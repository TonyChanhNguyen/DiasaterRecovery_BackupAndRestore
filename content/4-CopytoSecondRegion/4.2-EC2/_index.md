---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

### Copy EC2 AMI (Amazon Machine Image)

1 Click [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=ap-southeast-1#/) to navigate to the dashboard in **Singapore (ap-southeast-1)** region

2 Click **AMIs**

3 Verify the status of **BackupAndRestoreImage**backup is **Available**
  ![Copy AMI](/images/4.copytosecondregion/8_AIMCopy_1.png?width=90pc)
4 Click **BackupAndRestoreImage**. Click **Copy AMI** as the **Actions**
  ![Copy AMI](/images/4.copytosecondregion/9_AIMCopy_2.png?width=90pc)
5 Select **Sydney (ap-southeast-2** as the **Destination region**, then click ***Copy AMI*** button
  ![Copy AMI](/images/4.copytosecondregion/10_AIMCopy_3.png?width=90pc)
6 **EC2 AMI** copying process will be executed
  ![Copy AMI](/images/4.copytosecondregion/11_AIMCopy_4.png?width=90pc)
7 To check the result, we do the following:
 - Navigate to [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=ap-southeast-2#/) in **Sydney (ap-southeast-2)** region
 - Click **AMIs** and check AMI which had been copied from **Singapore (ap-southeast-1)** region
   ![Copy AMI](/images/4.copytosecondregion/12_AIMCopy_5.png?width=90pc)
