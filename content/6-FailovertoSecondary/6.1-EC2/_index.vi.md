---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 6.1 </b> "
---

### Triển khai một máy chủ EC2 từ AMI (Amazon Machine Image)

1 Nhấn [EC2](https://ap-southeast-2.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-2) để chuyển hướng đến trang chủ trong region **Sydney - (ap-southeast-2)**

2 Nhấn **AMIs**

3 Xác định trạng thái của **BackupAndRestoreImage** là  **Available**

   ![EC2](../../../images/6.failovertosecondary/8_EC2AMI.png?width=90pc)
   
4 Chọn **BackupAndRestoreImage**. Nhấn nút ***Launch instance from AMI***

   ![EC2](../../../images/6.failovertosecondary/9_EC2AMI.png?width=90pc)

5 Chọn loại máy chủ **t2.micro**, sau đó nhấn nút ***Next: Configure Instance Details***

   ![EC2](../../../images/6.failovertosecondary/10_EC2AMI.png?width=90pc)

6 Chọn **BackupAndRestore-S3InstanceProfile-xxxx** ở phần **IAM Role**, sau đó nhấn nút ***Next: Add Storage***

   ![EC2](../../../images/6.failovertosecondary/11_EC2AMI.png?width=90pc)

7 Nhấn nút ***Next: Add tags***

8 Thêm ```Name``` trong mục **Key** và ```BackupAndRestoreSecondary``` trong mục **Value**, sau đó nhấn nút ***Next: Configure Security Group***

   ![EC2](../../../images/6.failovertosecondary/12_EC2AMI.png?width=90pc)

9 Chọn **Create a new security group** và nhập ```backupandrestore-ap-southeast-ec2-SG``` trong mục **Security group name** và **Description**. Thêm các quy tắc như bên dưới bằng việc nhấn nút ***Add Rule***. Sau đó nhấn nút ***Review and Launch***

   ![EC2](../../../images/6.failovertosecondary/13_EC2AMI.png?width=90pc)

10 Nhấn nút ***launch***

11 Chọn **Proceed without a key pair**, chọn ô **I acknowledge that without a key pair,…**, sau đó nhấn nút ***Lauch Instances***

   ![EC2](../../../images/6.failovertosecondary/14_EC2AMI.png?width=90pc)

 {{% notice note %}}
Sao chép **Public IPv4 DNS** của máy chủ. Chúng ta sẽ sử dụng ở các bước sau
 {{% /notice %}}

![EC2](../../../images/6.failovertosecondary/15_EC2AMI.png?width=90pc)