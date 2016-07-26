# packer-win-aws
A Packer template for provisioning a windows instance on EC2 using Powershell over WinRM / https

# How to user

Ensure you have valid AWS account credentials in your shell.

Run `packer build template.json` to build the image.

# Sample output

```
$ packer build template.json
amazon-ebs output will be in this color.

==> amazon-ebs: Prevalidating AMI Name...
==> amazon-ebs: Inspecting the source AMI...
==> amazon-ebs: Creating temporary keypair: packer 5796c74b-046c-6431-95f9-a49bfa33567f
==> amazon-ebs: Creating temporary security group for this instance...
==> amazon-ebs: Authorizing access to port 5986 the temporary security group...
==> amazon-ebs: Launching a source AWS instance...
    amazon-ebs: Instance ID: i-adccc82b
==> amazon-ebs: Waiting for instance (i-adccc82b) to become ready...
==> amazon-ebs: Waiting for auto-generated password for instance...
    amazon-ebs: It is normal for this process to take up to 15 minutes,
    amazon-ebs: but it usually takes around 5. Please wait.
    amazon-ebs:  
    amazon-ebs: Password retrieved!
==> amazon-ebs: Waiting for WinRM to become available...
==> amazon-ebs: Connected to WinRM!
==> amazon-ebs: Provisioning with Powershell...
==> amazon-ebs: Provisioning with shell script: init.ps1
    amazon-ebs:
    amazon-ebs:
    amazon-ebs: Directory: C:\
    amazon-ebs:
    amazon-ebs:
    amazon-ebs: Mode                LastWriteTime     Length Name
    amazon-ebs: ----                -------------     ------ ----
    amazon-ebs: d----        11/18/2014   7:08 PM            inetpub
    amazon-ebs: d----         8/22/2013   3:52 PM            PerfLogs
    amazon-ebs: d-r--        11/18/2014   7:09 PM            Program Files
    amazon-ebs: d----        11/18/2014   7:12 PM            Program Files (x86)
    amazon-ebs: d-r--        11/18/2014   7:09 PM            Users
    amazon-ebs: d----        11/18/2014   8:03 PM            Windows
==> amazon-ebs: Stopping the source instance...
==> amazon-ebs: Waiting for the instance to stop...
==> amazon-ebs: Creating the AMI: windows-ami 1469499211
    amazon-ebs: AMI: ami-c6018bd1
==> amazon-ebs: Waiting for AMI to become ready...
==> amazon-ebs: Terminating the source AWS instance...
==> amazon-ebs: Cleaning up any extra volumes...
==> amazon-ebs: No volumes to clean up, skipping
==> amazon-ebs: Deleting temporary security group...
==> amazon-ebs: Deleting temporary keypair...
Build 'amazon-ebs' finished.

==> Builds finished. The artifacts of successful builds are:
--> amazon-ebs: AMIs were created:

us-east-1: ami-c6018bd1
```
