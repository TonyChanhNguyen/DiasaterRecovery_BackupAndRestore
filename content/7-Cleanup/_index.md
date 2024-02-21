---
title : "Clean up Resources"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

### Amazon S3

1 Click [S3](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1) to navigate to the dashboard

2 Select the bucket with prefix **backupandrestore-uibucket-xxxx** and click ***Empty*** button

 ![Cleanup](../images/7.cleanup/1_S3Clean.png?width=90pc)

3 Enter ```permanently delete``` into the confirmation box and then click ***Empty*** button

 ![Cleanup](../images/7.cleanup/2_S3Clean.png?width=90pc)

4 Wait until you see the green banner across the top of the page, indicating the bucket is empty. Then click ***Exit*** button

 ![Cleanup](../images/7.cleanup/3_S3Clean.png?width=90pc)

{{% notice note %}}
Repeat from step **1.1** to step **1.4** with the bucket have prefix ```backupandrestore-uibucket-xxxx-dr```
 {{% /notice %}}

### Amazon CloudFormation

1 Click [CloudFormation](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1) to navigate to the dashboard in **Singapore - (ap-southeast-1)** region

2 Select **BackupAndRestore** stack and click ***Delete*** button

 ![Cleanup](../images/7.cleanup/4_CloudformationClean.png?width=90pc)

3 Click ***Delete stack*** button to confirm

 ![Cleanup](../images/7.cleanup/5_CloudformationClean.png?width=90pc)

### AWS Backup 

1 Click [AWS Backup](https://ap-southeast-2.console.aws.amazon.com/backup/home?region=ap-southeast-2#/) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

2 Click **Backup Vaults** and click**Default**

 ![Cleanup](../images/7.cleanup/6_BackupClean.png?width=90pc)

3 Select all of backups and click **Actions**, then click **Delete**

 ![Cleanup](../images/7.cleanup/7_BackupClean.png?width=90pc)

4 Click ***Confirm*** button

 ![Cleanup](../images/7.cleanup/8_BackupClean.png?width=90pc)

{{% notice note %}}
Repeat form step **3.1** to step **3.3** for [AWS Backup](https://ap-southeast-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#/)
 in **Singapore - (ap-southeast-1)** region
  {{% /notice %}}

 ### Amazon RDS

 1 Click [RDS](https://ap-southeast-2.console.aws.amazon.com/rds/home?region=ap-southeast-2#databases:) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

 2 Select **backupandrestore-secondary-region** database. Click **Actions**, then click **Delete**

 ![Cleanup](../images/7.cleanup/9_RDSClean.png?width=90pc)

 3 Disable **Create final snapshot** and **Retain automated backups** checkbox. Next, enable **I acknowledgement …** checkbox. Enter ```delete me``` into the confirmation box. Click ***Delete*** button

 ![Cleanup](../images/7.cleanup/10_RDSClean.png?width=90pc)

 ### Amazon EC2

 1 Click [EC2](https://ap-southeast-2.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-2#Instances:) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

 2 Select instance with **Name** is **BackupAndRestoreSecondary** and click **Instance State**, then click **Terminate instance.**

 ![Cleanup](../images/7.cleanup/11_EC2Clean.png?width=90pc)

 3 Click **AMIs** and select **AMI** with **AMI Name** is **BackupAndRestoreImage**. Click **Actions** and click **Deregister AMI**

 ![Cleanup](../images/7.cleanup/12_EC2Clean.png?width=90pc)

 4 Click ***Deregister AMI*** buton

 ![Cleanup](../images/7.cleanup/13_EC2Clean.png?width=90pc)

 5 Click **Security groups**. Select all of created **security groups**  **backupandrestore-ap-southeast-ec2-SG** and **backupandrestore-ap-southeast-rds-SG**. Click **Actions** and click **Delete security groups**

 ![Cleanup](../images/7.cleanup/14_EC2Clean.png?width=90pc)

 6 Click ***Delete*** button

 {{% notice info %}}
Repeat from step **5.4** to step **5.6** for [EC2](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#Instances:)
 in **Singapore - (ap-southeast-1)** region {{% /notice %}}