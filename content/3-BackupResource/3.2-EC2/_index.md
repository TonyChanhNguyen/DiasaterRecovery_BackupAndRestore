---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2 </b> "
---

### Create an AMI (Amazon Machine Image)

If EC2 instance contain apllication data, it would be necessary to schedule recurring backups to meet target RPO. [AWS Backup](https://aws.amazon.com/vi/backup/) provides this functionality through a dashboard that make it simple to audit backup and restore activity across AWS services. Sinces our instance contain no data, only code, we will create a backup on time.

Reoccurring backups are necessary for a production application every time a change occurs to the EC2 instance.

1 Click [EC2](https://ap-southeast-1.console.aws.amazon.com/ec2/home?region=ap-southeast-1#Home:) to navigate to the **EC2** dashboard in **Singapore (ap-southeast-1)** region

2 Click **Instances (running)**

 ![EC2](../../images/3.backupresources/5_EC2Dashboard.png?width=90pc)

3 Select **UniShopAppV1EC2BackupAndRestore**. Click ***Action* ->** ***Images and Templates* ->** ***Create image***

  ![EC2](../../images/3.backupresources/6_AIMCreate.png?width=90pc)

4 Enter ```BackupAndRestoreImage``` as the **Image Name**, then click ***Next*** button to create

  ![EC2](../../images/3.backupresources/7_AIMCreating.png?width=90pc)

5 Select **AMI** and see AMI creating

  ![EC2](../../images/3.backupresources/8_AIMCreating_1.png?width=90pc)

6 After **AMI** was created successfully, we will get the result same as below

  ![EC2](../../images/3.backupresources/9_AIMCreated.png?width=90pc)