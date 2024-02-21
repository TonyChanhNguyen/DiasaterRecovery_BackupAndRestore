---
title : "RDS"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 6.2 </b> "
---

### Khôi phục CSDL RDS

1 Nhấn [AWS Backup](https://ap-southeast-2.console.aws.amazon.com/backup/home?region=ap-southeast-2#) để chuyển hướng đến trang chủ trong region **Sydney - (ap-southeast-2)**

2 Nhấn vào **Backup Vaults**, sau đó nhấn  **Default**

 ![RDS Restore](../../../images/6.failovertosecondary/16_RDSRestore.png?width=90pc)

3 Trong phần **Backups**, chọn bản sao lưu. Sau đó nhấn **Restore** trong mục **Actions**

 ![RDS Restore](../../../images/6.failovertosecondary/17_RDSRestore.png?width=90pc)

 {{% notice warning %}}
Nếu bạn không thấy bản sao lưu, kiểm tra trạng thái của **Copy Job**. Nhấn [AWS Backup](https://ap-southeast-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#) để chuyển hướng đến trang chủ trong region **Singapore - (ap-southeast-1)**. Nhấn **Jobs**, sau đó nhấn **Copy jobs**. Xác định **Status** của bản sao lưu là **Completed**
 {{% /notice %}}

 ![RDS Restore](../../../images/6.failovertosecondary/18_RDSRestore.png?width=90pc)

4 Trong phần **Settings**, nhập ```backupandrestore-secondary-region``` ở mục **DB Instance Identifier**. Ở phần **Network & Security**, chọn **ap-southeast-1x** ở phần **Availability zone**

 ![RDS Restore](../../../images/6.failovertosecondary/19_RDSRestore.png?width=90pc)

5 Nhấn nút ***Restore backup***

 ![RDS Restore](../../../images/6.failovertosecondary/20_RDSRestore.png?width=90pc)

6 Quá trình khôi phục bản sao RDS đang được tiến hành

 ![RDS Restore](../../../images/6.failovertosecondary/21_RDSRestore.png?width=90pc)

### Cấu hình Security Group

1 Nhấn [VPC](https://ap-southeast-2.console.aws.amazon.com/vpc/home?region=ap-southeast-2#) để chuyển hướng đến trang chủ trong reigon **Sydney - (ap-southeast-2)**

2 Nhấn vào **Security Groups**, sau đó nhấn nút ***Create security group***

 ![Security Group](../../../images/6.failovertosecondary/22_SGCreate.png?width=90pc)

3 Ở phần **Basic details**, nhập ```backupandrestore-ap-southeast-rds-SG``` tại mục **Security group name** và **Description**

 ![Security Group](../../../images/6.failovertosecondary/23_SGCreate.png?width=90pc)

4 Ở phần **Inbound Rules**, nhấn nút ***Add rule***. Chọn **Type** là **MYSQL/Aurora**. Chọn **Source** là **Custom** và chọn **backupandrestore-us-west-ec2-SG**. Việc này sẽ cho phép giao tiếp giữa máy chủ EC2 và máy chủ RDS. Sau đó nhấn nút ***Create security group***

 ![Security Group](../../../images/6.failovertosecondary/24_SGCreate.png?width=90pc)

### Cấu hình RDS

1 Nhấn [RDS](https://ap-southeast-2.console.aws.amazon.com/rds/home?region=ap-southeast-2) để chuyển hướng đến trang chủ trong region **Sydney - (ap-southeast-2)**

2 Nhấn chọn **DB Instances**

 ![RDS Modify](../../../images/6.failovertosecondary/25_RDSModify.png?width=90pc)

3 Chọn **backupandrestore-secondary-region**, sau đó nhấn nút ***Modify***

 {{% notice note %}}
 CSDL RDS phải có **Status** là **Available**
 {{% /notice %}}
 ![RDS Modify](../../../images/6.failovertosecondary/26_RDSModify.png?width=90pc)

 4 Ở phần **Connectivity**, chọn **Security group** là **backupandrestore-ap-southeast-rds-SG**. Sau đó nhấn nút ***Continue***

 ![RDS Modify](../../../images/6.failovertosecondary/27_RDSModify.png?width=90pc)

 5 Chọn **Apply immediately** và nhấn nút ***Apply immediately***

 ![RDS Modify](../../../images/6.failovertosecondary/28_RDSModify.png?width=90pc)

 6 Nhấn chọn **backupandrestore-secondary-region**

 ![RDS Modify](../../../images/6.failovertosecondary/29_RDSModify.png?width=90pc)
  {{% notice note %}}
Sao chép địa chỉ **Endpoint** và **Port**. Chúng ta sẽ sử dụng ở các bước sau.
 {{% /notice %}}

 ![RDS Modify](../../../images/6.failovertosecondary/30_RDSModify.png?width=90pc)