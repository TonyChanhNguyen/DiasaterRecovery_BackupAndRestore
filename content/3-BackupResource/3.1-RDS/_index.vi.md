---
title : "RDS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1 </b> "
---

### Sao lưu cơ sở dữ liệu RDS

1 Click [AWS Backup](https://ap-southeast-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#/) để chuyển hướng đến trang chủ của **AWS Backup** ở Region **Singapore (ap-southeast-1)**

2 Click chọn ***Protected resources***, sau đó cilck chọn nút ***Create an on-demand backup***

 ![RDS Backup](../../../images/3.backupresources/1_ProtectedResources.png?width=90pc)

3 Lựa chọn **RDS** ở mục **Resource type**, sau đó chọn **unishopappv1dbbackupandrestore** (RDS Database đã được tạo bằng Cloudformation ở phần [Region chính](../../2-pre-requisites/2.2-primaryregion)) ở mục **Database name**. 
Nhấn nút ***Create on-demand backup*** để bắt đầu khởi tạo

 ![RDS Backup](../../../images/3.backupresources/2_CreateBackup.png?width=90pc)

{{% notice warning %}} 
Nếu gặp lỗi, hãy **LẶP LẠI** từ bước 1.1 đến 1.3 ở trên và chắc chắn rằng bạn bắt đầu từ bước 1.1 
{{% /notice  %}}

4 Sau đó bản sao lưu cơ sở dữ liệu sẽ được tạo

 ![RDS Backup](../../../images/3.backupresources/3_CreatingBackup.png?width=90pc)

{{% notice info %}} 
Quá trình này mất ít nhất 10 phút để hoàn thành
{{% /notice  %}}

5 Sau khi quá trình sao lưu hoàn tất, chúng ta sẽ thu được kết quả như bên dưới

 ![RDS Backup](../../../images/3.backupresources/4_CreatedBackup.png?width=90pc)
