---
title : "Primary Region"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

 ### Lauch a Amazon CloudFormation Template

1 Create an application in primary region **Singapore (ap-southeast-1)** by lauching this [**CloudFormation Template**](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks/create/template?stackName=BackupAndRestore&templateURL=https://ee-assets-prod-us-east-1.s3.amazonaws.com/modules/630039b9022d4b46bb6cbad2e3899733/v1/BackupAndRestore.yaml) 

2 Click the ***Next*** button 

 ![Cloudformation Template](../../images/2.prerequisites/8_CloudformationTemplate.png?width=90pc)

3 Click the ***Next*** button 

{{% notice info %}} 
Set LatestAmiId as the default values
{{% /notice  %}}

  ![Cloudformation Template](../../images/2.prerequisites/9_CloudformationTemplate_1.png?width=90pc)

4 Click the ***Next*** button 

 ![Cloudformation Template](../../images/2.prerequisites/10_CloudformationTemplate_2.png?width=90pc)

5 Scroll down to the end of page, enable **I acknowledge that AWS CloudFormation might create IAM resources with custom names** checkbox, then click ***Create stack*** button

  ![Cloudformation Template](../../images/2.prerequisites/11_CloudformationTemplate_3.png?width=90pc)

6 **Cloudformation** is creating necessary resources

 ![Cloudformation Template](../../images/2.prerequisites/12_CloudformationTemplate_4.png?width=90pc)

{{% notice note %}} 
This process takes at least 15 minutes to finish
{{% /notice %}}

7 After finishing you will get the result same as below

 ![Cloudformation Template](../../images/2.prerequisites/13_CloudformationTemplate_Result.png?width=90pc)

8 To verify application that had been created, access [S3](https://console.aws.amazon.com/s3/home?region=ap-southeast-1#/) at **Bucket** we will see a bucket with prefix ```backupandrestore-uibucket-xxxx```

 ![Application Result](../../images/2.prerequisites/14_ApplicationResult_1_1.png?width=90pc)

9 Select the bucket which had been created, scroll down to the end of **Permission**. Copy **Bucket website endpoint** of **S3 Bucket** 

 ![Application Result](../../images/2.prerequisites/15_ApplicationResult_2.png?width=90pc)

 ![Application Result](../../images/2.prerequisites/16_ApplicationResult_3.png?width=90pc)

10 Enter copied endpoint to any internet explorer . Then we will get the result same as below, **The Unicorn Shop** application had been created at **Singapore (ap-southeast-1)** region

 ![Application Result](../../images/2.prerequisites/17_ApplicationResult_4.png?width=90pc)