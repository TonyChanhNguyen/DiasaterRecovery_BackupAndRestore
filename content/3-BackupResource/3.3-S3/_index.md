---
title : "S3"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3 </b> "
---

  ### Create S3 UI bucket in secondary **Sydney (ap-southeast-2)**

 1 Click [S3](https://s3.console.aws.amazon.com/s3/buckets) to navigate to the **S3** dashboard

 2 Copy name of **UI bucket** in **Singapore (ap-southeast-1)** region. It will have prefix ```backupandrestore-uibucket-xxxx```

 ![S3 Bucket](/images/3.backupresources/10_S3Bucket.png?width=90pc)

 3 Click ***Create bucket*** button

 ![S3 Bucket](/images/3.backupresources/11_S3BucketCreating.png?width=90pc)

 4 Enter name of bucket use for **UI Bucket** that you had copied at step 2 and add "**-dr**" at the end

 5 Select **Sydney (ap-southeast-2)** as the **AWS Region**

  ![S3 Bucket](/images/3.backupresources/12_S3BucketCreating_1.png?width=90pc)

 6 In **Object Ownership**. Select **ACLs enabled**
 
  ![S3 Bucket](/images/3.backupresources/13_S3BucketCreating_2.png?width=90pc)

 7 In **Block Public Access settings for this bucket**  section. Disable **Block *all* public access** checkbox include children.
 Enable **I acknowledge that the current settings….** checkbox

  ![S3 Bucket](/images/3.backupresources/14_S3BucketCreating_3.png?width=90pc)

 8 Click ***Create Bucket***  button to create **S3 Bucket**

  ![S3 Bucket](/images/3.backupresources/15_S3BucketCreating_4.png?width=90pc)

 9 After **S3 Bucket** was created successfully, we will get the result same as below

  ![S3 Bucket](/images/3.backupresources/16_S3BucketCreated.png?width=90pc)