---
title : "RDS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

### Sao chép RDS Backup
1 Click chọn [AWS Backup](https://us-east-1.console.aws.amazon.com/backup/home?region=ap-southeast-1#/) để chuyển hướng vào trang chủ ở region **Singapore (ap-southeast-1)**

2 Chọn **Backup Vaults**, sau đó chọn **Default** 
  ![Copy Backup](/images/4.copytosecondregion/1_BackupVault.png?width=90pc)
3 Trong phần **Backups**, chọn bản sao lưu vừa được tạo. Sau đó nhấn **Copy** ở mục **Actions**
  ![Copy Backup](/images/4.copytosecondregion/2_CopyBackup.png?width=90pc)
  {{% notice warning %}}
   Nếu không tìm thấy mục bản sao lưu, kiểm tra trạng thái của **Backup Job**. Chọn **Jobs**, sau đó chọn **Backup Jobs**. Xác nhận **Status** bản sao lưu của bạn là **Completed**
   ![Copy Backup](/images/4.copytosecondregion/5_Backupjob.png?width=90pc)
 {{% /notice %}}

4 Chọn **Sydney (ap-southeast-2)** tại mục **Copy to destination**, sau đó nhấn nút ***Copy***
   ![Copy Backup](/images/4.copytosecondregion/3_CopyVault_1.png?width=90pc)

5 Quá trình sao chép bản sao lưu từ region **Singapore (ap-southeast-1)** sang region **Sydney (ap-southeast-2)** đang được khởi tạo 
    ![Copy Backup](/images/4.copytosecondregion/4_CopyVault_2.png?width=90pc)

  {{% notice info %}}
  Quá trình này mất khoảng 10 phút để hoàn thành
  {{% /notice %}}

6 Để kiểm tra kết quả, ta thực hiện: 
- Chuyển hướng đến [AWS Backup](https://ap-southeast-2.console.aws.amazon.com/backup/home?region=ap-southeast-2#/) trên region **Sydney (ap-southeast-2)**
- Vào phần **Backup vaults**, chọn **Backup vaults** là **Default** 
  ![Copy Backup](/images/4.copytosecondregion/6_VerifyBackup_1.png?width=90pc)
- Ở mục **Backups** chúng ta sẽ thấy bản sao lưu được sao chép từ region **Singapore (ap-southeast-1)**
  ![Copy Backup](/images/4.copytosecondregion/7_VerifyBackup_2.png?width=90pc)