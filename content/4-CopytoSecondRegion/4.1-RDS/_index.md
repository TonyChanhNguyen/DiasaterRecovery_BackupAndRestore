---
title : "RDS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b>4.1 </b> "
---

### Copy RDS Backup
1 Click [AWS Backup](https://us-east-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#/) to navigate to the dashboard in **Singapore (ap-southeast-1)** region

2 Click **Backup Vaults**, then click **Default** 
  ![Copy Backup](/images/4.copytosecondregion/1_BackupVault.png?width=90pc)
3 At **Backups**, select backup. Then click **Copy** as the **Actions**
  ![Copy Backup](/images/4.copytosecondregion/2_CopyBackup.png?width=90pc)
  {{% notice warning %}}
   If you don't see your backup, check the status of **Backup Job**. Click **Jobs**, then click **Backup Jobs**. Verify **Status** of your backup is **Completed**
   ![Copy Backup](/images/4.copytosecondregion/5_Backupjob.png?width=90pc)
 {{% /notice %}}

4 Select **Sydney (ap-southeast-2)** as the **Copy to destination**, then click ***Copy*** button
   ![Copy Backup](/images/4.copytosecondregion/3_CopyVault_1.png?width=90pc)

5 The process of copying backup from **Singapore (ap-southeast-1)** region to **Sydney (ap-southeast-2)** region is executing
    ![Copy Backup](/images/4.copytosecondregion/4_CopyVault_2.png?width=90pc)

  {{% notice info %}}
  This process will take about 10 minutes to complete
  {{% /notice %}}

6 To check the result, we do the following: 
- Navigate to [AWS Backup](https://ap-southeast-2.console.aws.amazon.com/backup/home?region=ap-southeast-2#/) in **Sydney (ap-southeast-2)** region
- At **Backup vaults**, select **Backup vaults** as **Default** 
  ![Copy Backup](/images/4.copytosecondregion/6_VerifyBackup_1.png?width=90pc)
- At **Backups** we will see the backup which was copied from **Singapore (ap-southeast-1)** region
  ![Copy Backup](/images/4.copytosecondregion/7_VerifyBackup_2.png?width=90pc)