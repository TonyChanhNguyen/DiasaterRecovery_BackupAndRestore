---
title : "RDS"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 6.2 </b> "
---

 ### Restore RDS database

1 Click [AWS Backup](https://ap-southeast-2.console.aws.amazon.com/backup/home?region=ap-southeast-2#) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

2 Click **Backup Vaults**, then click  **Default**

 ![RDS Restore](/images/6.failovertosecondary/16_RDSRestore.png?width=90pc)

3 At **Backups**, select backup. Then click **Restore** of **Actions**

 ![RDS Restore](/images/6.failovertosecondary/17_RDSRestore.png?width=90pc)

 {{% notice warning %}}
If you don't see your backup, check the status of **Copy Job**. Click [AWS Backup](https://ap-southeast-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#) to navigate to the dashboard in **Singapore - (ap-southeast-1)** region. Click **Jobs**, then click **Copy jobs**. Verify **Status** of backup is **Completed**
 {{% /notice %}}

 ![RDS Restore](/images/6.failovertosecondary/18_RDSRestore.png?width=90pc)

4 At **Settings**, enter ```backupandrestore-secondary-region``` as the **DB Instance Identifier**. At **Network & Security**, select **ap-southeast-1x** as the **Availability zone**

 ![RDS Restore](/images/6.failovertosecondary/19_RDSRestore.png?width=90pc)

5 Click ***Restore backup***

 ![RDS Restore](/images/6.failovertosecondary/20_RDSRestore.png?width=90pc)

6 The restoring RDS backup process is executing

 ![RDS Restore](/images/6.failovertosecondary/21_RDSRestore.png?width=90pc)

### Configure Security Group

1 Click [VPC](https://ap-southeast-2.console.aws.amazon.com/vpc/home?region=ap-southeast-2#) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

2 Click **Security Groups**, then click ***Create security group*** button

 ![Security Group](/images/6.failovertosecondary/22_SGCreate.png?width=90pc)

3 At **Basic details**, enter ```backupandrestore-ap-southeast-rds-SG``` as the **Security group name** and **Description**

 ![Security Group](/images/6.failovertosecondary/23_SGCreate.png?width=90pc)

4 At **Inbound Rules**, click ***Add rule*** button. Select **Type** as the **MYSQL/Aurora**. Select **Source** as the **Custom** and select **backupandrestore-us-west-ec2-SG**. This will allow the communication between your EC2 instance and your RDS instance. Then click ***Create security group*** button

 ![Security Group](/images/6.failovertosecondary/24_SGCreate.png?width=90pc)

### Configure RDS

1 Click [RDS](https://ap-southeast-2.console.aws.amazon.com/rds/home?region=ap-southeast-2) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

2 Click **DB Instances**

 ![RDS Modify](/images/6.failovertosecondary/25_RDSModify.png?width=90pc)

3 Click **backupandrestore-secondary-region**, then click ***Modify*** button

 {{% notice note %}}
 RDS database must have **Status** is **Available**
 {{% /notice %}}
 ![RDS Modify](/images/6.failovertosecondary/26_RDSModify.png?width=90pc)

 4 At **Connectivity**, select **Security group** is **backupandrestore-ap-southeast-rds-SG**. Then click ***Continue*** button

 ![RDS Modify](/images/6.failovertosecondary/27_RDSModify.png?width=90pc)

 5 Click **Apply immediately** then click ***Apply immediately*** button

 ![RDS Modify](/images/6.failovertosecondary/28_RDSModify.png?width=90pc)

 6 Click **backupandrestore-secondary-region**

 ![RDS Modify](/images/6.failovertosecondary/29_RDSModify.png?width=90pc)
  {{% notice note %}}
Copy **Endpoint** address and **Port**. We will use it for next steps.
 {{% /notice %}}

 ![RDS Modify](/images/6.failovertosecondary/30_RDSModify.png?width=90pc)