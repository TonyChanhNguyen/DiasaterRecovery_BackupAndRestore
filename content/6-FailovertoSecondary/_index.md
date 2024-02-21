---
title : "Failover to Secondary"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

When a regional service event affects to Unicorn application in primary region **Singapore (ap-southeast-1)**, we want to bring up resources in the secondary region **Sydney (ap-southeast-2)**.

We assume a regional service event has occurred. In this section, we will manually perform a series of tasks to bring up the application in the secondary region N. California (us-west-1). In a production environment, we would automate these steps using an AWS Cloudformation template or third-party tools.

We will perform the following:
 - Launch a EC2 instancec from AMI (Amazon Machine Image)
 - Restore RDS database from backup
 - Configure the application

### Simulating a Regional Service Event

We will new simulate a regional service event affecting the S3 static website in **Singapore (ap-southeast-1)** region that website The Unicorn Shop running

1 Click [S3](https://s3.console.aws.amazon.com/s3/home?region=ap-southeast-1#) to navigate to the dashboard

2 Click **backupandrestore-uibucket-xxxx** bucket
   ![Failover to Secondary](/images/6.failovertosecondary/1_S3Bucket.png?width=90pc)
3 Click **Permissions**. At **Block public access (bucket settings)**, click ***Edit*** button
   ![Failover to Secondary](/images/6.failovertosecondary/2_S3Bucket.png?width=90pc)
4 Enable **Block all public access** checkbox, then click ***Save*** button for saving
   ![Failover to Secondary](/images/6.failovertosecondary/3_S3Bucket.png?width=90pc)
5 Enter ```confirm```, then click ***Confirm*** button
   ![Failover to Secondary](/images/6.failovertosecondary/4_S3Bucket.png?width=90pc)
6 Click **Properties**
   ![Failover to Secondary](/images/6.failovertosecondary/5_S3Bucket.png?width=90pc)
7 At **Static website hosting**,Click **Bucket website endpoint** link
   ![Failover to Secondary](/images/6.failovertosecondary/6_S3Bucket.png?width=90pc)
8 You will see the **403 Forbidden** error
   ![Failover to Secondary](/images/6.failovertosecondary/7_S3Bucket.png?width=90pc)

