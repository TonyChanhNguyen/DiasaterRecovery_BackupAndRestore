---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 7 </b> "
---

### Amazon S3

1 Nhấn [S3](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1) để chuyển hướng đến trang chủ

2 Chọn bucket với tiền tố **backupandrestore-uibucket-xxxx** và nhấn nút ***Empty***

 ![Cleanup](../../images/7.cleanup/1_S3Clean.png?width=90pc)

3 Nhập ```permanently delete``` vào ô xác nhận và nhấn nút ***Empty***

 ![Cleanup](../../images/7.cleanup/2_S3Clean.png?width=90pc)

4 Chờ đến khi bạn thấy ô màu xanh lá cây ở phía trên của trang chủ, thể hiện bucket đã rỗng. Sau đó nhấn nút ***Exit***

 ![Cleanup](../../images/7.cleanup/3_S3Clean.png?width=90pc)

{{% notice note %}}
Thực hiện lặp lại bước **1.1** đến **1.4** đối với bucket có tiền tố ```backupandrestore-uibucket-xxxx-dr```
 {{% /notice %}}

### Amazon CloudFormation

1 Nhấn [CloudFormation](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1) để chuyển hướng đến trang chủ trong region **Singapore - (ap-southeast-1)**

2 Chọn stack **BackupAndRestore** và nhấn nút ***Delete***

 ![Cleanup](../../images/7.cleanup/4_CloudformationClean.png?width=90pc)

3 Nhấn nút ***Delete stack*** để xác nhận 

 ![Cleanup](../../images/7.cleanup/5_CloudformationClean.png?width=90pc)

### AWS Backup 

1 Nhấn [AWS Backup](https://ap-southeast-2.console.aws.amazon.com/backup/home?region=ap-southeast-2#/) để chuyển hướng đến trang chủ ở region **Sydney - (ap-southeast-2)**

2 Nhấn **Backup Vaults** và chọn **Default**

 ![Cleanup](../../images/7.cleanup/6_BackupClean.png?width=90pc)

3 Chọn tất cả bản sao lưu và chọn **Actions**, sau đó chọn **Delete**

 ![Cleanup](../../images/7.cleanup/7_BackupClean.png?width=90pc)

4 Nhấn nút ***Confirm***

 ![Cleanup](../../images/7.cleanup/8_BackupClean.png?width=90pc)

{{% notice note %}}
Thực hiện lặp lại bước **3.1** đến **3.3** cho [AWS Backup](https://ap-southeast-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#/)
 trong region **Singapore - (ap-southeast-1)** {{% /notice %}}

 ### Amazon RDS

 1 Nhấn [RDS](https://ap-southeast-2.console.aws.amazon.com/rds/home?region=ap-southeast-2#databases:) để chuyển hướng đến trang chủ ở region **Sydney - (ap-southeast-2)**

 2 Chọn CSDL **backupandrestore-secondary-region**. Chọn **Actions**, sau đó chọn **Delete**

 ![Cleanup](../../images/7.cleanup/9_RDSClean.png?width=90pc)

 3 Bỏ chọn ô **Create final snapshot** và **Retain automated backups**. Tiếp theo, chọn ô **I acknowledgement …**. Nhập ```delete me``` vào ô xác nhận. Nhấn nút ***Delete***

 ![Cleanup](../../images/7.cleanup/10_RDSClean.png?width=90pc)

 ### Amazon EC2

 1 Nhấn [EC2](https://ap-southeast-2.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-2#Instances:) để chuyển hướng đến trang chủ ở region **Sydney - (ap-southeast-2)**

 2 Chọn máy chủ có **Name** là **BackupAndRestoreSecondary** và nhấn **Instance State**, sau đó nhấn **Terminate instance.**

 ![Cleanup](../../images/7.cleanup/11_EC2Clean.png?width=90pc)

 3 Nhấn **AMIs** và chọn **AMI** có **AMI Name** là **BackupAndRestoreImage**. Nhấn **Actions** và chọn **Deregister AMI**

 ![Cleanup](../../images/7.cleanup/12_EC2Clean.png?width=90pc)

 4 Nhấn nút ***Deregister AMI***

 ![Cleanup](../../images/7.cleanup/13_EC2Clean.png?width=90pc)

 5 Nhấn **Security groups**. Chọn tất cả **security groups** được tạo **backupandrestore-ap-southeast-ec2-SG** và **backupandrestore-ap-southeast-rds-SG**. Nhấn **Actions** và chọn **Delete security groups**

 ![Cleanup](../../images/7.cleanup/14_EC2Clean.png?width=90pc)

 6 Nhấn nút ***Delete***

 {{% notice info %}}
Thực hiện lặp lại bước **5.4** đến **5.6** cho [EC2](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#Instances:)
 trong region **Singapore - (ap-southeast-1)** {{% /notice %}}