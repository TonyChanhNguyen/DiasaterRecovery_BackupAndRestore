---
title : "RDS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b>3.1 </b> "
---

### Backup RDS database

1 Click [AWS Backup](https://ap-southeast-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#/) to navigate to the dashboard **AWS Backup** at **Singapore (ap-southeast-1)** region

2 Click ***Protected resources***, then cilck ***Create an on-demand backup*** button

 ![RDS Backup](../../images/3.backupresources/1_ProtectedResources.png?width=90pc)

3 Select **RDS** as the **Resource type**, then select **unishopappv1dbbackupandrestore** (RDS Database which was created by Cloudformation at [Region chính](../../2-pre-requisites/2.2-primaryregion)) as the **Database name**. 
Click the ***Create on-demand backup*** button

 ![RDS Backup](../../images/3.backupresources/2_CreateBackup.png?width=90pc)

{{% notice warning %}} 
If you see error, please **REPEAT** from step 1.1 to 1.3 above and make sure you start from step 1.1
{{% /notice  %}}

4 RDS database backup will be created after

 ![RDS Backup](../../images/3.backupresources/3_CreatingBackup.png?width=90pc)

{{% notice info %}} 
This process will take at least 10 minutes to finish
{{% /notice  %}}

5 After backup process finish, we will get the result same as below

 ![RDS Backup](../../images/3.backupresources/4_CreatedBackup.png?width=90pc)
