---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b>6.1 </b> "
---

### Launch an EC2 instance from AMI (Amazon Machine Image)

1 Click [EC2](https://ap-southeast-2.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-2) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

2 Click **AMIs**

3 Verify the status of **BackupAndRestoreImage** is  **Available**

   ![EC2](/images/6.failovertosecondary/8_EC2AMI.png?width=90pc)
   
4 Select **BackupAndRestoreImage**. Click ***Launch instance from AMI*** button

   ![EC2](/images/6.failovertosecondary/9_EC2AMI.png?width=90pc)

5 Select **t2.micro** instance type, then click ***Next: Configure Instance Details*** button

   ![EC2](/images/6.failovertosecondary/10_EC2AMI.png?width=90pc)

6 Select **BackupAndRestore-S3InstanceProfile-xxxx** as the **IAM Role**, then click ***Next: Add Storage*** button

   ![EC2](/images/6.failovertosecondary/11_EC2AMI.png?width=90pc)

7 Click ***Next: Add tags*** button

8 Add ```Name``` as the **Key** and ```BackupAndRestoreSecondary```as the **Value**, then click ***Next: Configure Security Group*** button

   ![EC2](/images/6.failovertosecondary/12_EC2AMI.png?width=90pc)

9 Select **Create a new security group** and enter ```backupandrestore-ap-southeast-ec2-SG``` as the **Security group name** and **Description**. Add rules same as below by clicking the ***Add Rule*** button. Then click ***Review and Launch*** button

   ![EC2](/images/6.failovertosecondary/13_EC2AMI.png?width=90pc)

10 Click ***launch*** button

11 Select **Proceed without a key pair**, enable **I acknowledge that without a key pair,…** checkbox, then click ***Lauch Instances*** button

   ![EC2](/images/6.failovertosecondary/14_EC2AMI.png?width=90pc)

 {{% notice note %}}
Copy **Public IPv4 DNS** of the instance. We will use it for next steps
 {{% /notice %}}

![EC2](/images/6.failovertosecondary/15_EC2AMI.png?width=90pc)