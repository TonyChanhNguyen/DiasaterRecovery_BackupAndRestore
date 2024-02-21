---
title : "Backup Resource"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

Now we are going to backup our resources

We will perform the following:
 - Backup the RDS database
 - Create an EC2 AMI (Amazon Machine Image)
 - Create a new S3 UI bucket 

We will create a [backup plan](https://docs.aws.amazon.com/aws-backup/latest/devguide/creating-a-backup-plan.html) for a production application and schedule recurring backups to meet target RPO.

However, for this workshop, we will create a **manual backup**
