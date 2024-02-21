---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2 </b> "
---

### Tạo một AMI (Amazon Machine Image)

Nếu máy chủ EC2 chứa dữ liệu ứng dụng, việc tạo kế hoạch sao lưu định kỳ để đạt mục tiêu RPO là rất cần thiết. [AWS Backup](https://aws.amazon.com/vi/backup/) có khả năng thực hiện điều này thông qua giao diện giúp dễ dàng để kiểm tra hoạt động sao lưu và phục hồi thông qua dịch vụ AWS. Bởi vì máy chủ của chúng ta không chứa dữ liệu, chỉ có code, chúng ta sẽ tạo một bản sao lưu một lần. 

Các bản sao lưu định kỳ rất cần thiết cho một sản phẩm ứng dụng một khi có một thay đổi xảy đến máy chủ EC2.

1 Click [EC2](https://ap-southeast-1.console.aws.amazon.com/ec2/home?region=ap-southeast-1#Home:) để chuyển hướng đến trang chủ **EC2** ở region **Singapore (ap-southeast-1)**

2 Click **Instances (running)**

 ![EC2](/images/3.backupresources/5_EC2Dashboard.png?width=90pc)

3 Chọn **UniShopAppV1EC2BackupAndRestore**. Click ***Action* ->** ***Images and Templates* ->** ***Create image***

  ![EC2](/images/3.backupresources/6_AIMCreate.png?width=90pc)

4 Nhập ```BackupAndRestoreImage``` vào mục **Image Name**, sau đó click nút ***Next*** để khởi tạo

  ![EC2](/images/3.backupresources/7_AIMCreating.png?width=90pc)

5 Chọn mục **AMI** và xem AMI đang được khởi tạo 

  ![EC2](/images/3.backupresources/8_AIMCreating_1.png?width=90pc)

6 Sau khi **AMI** được khởi tạo thành công, chúng ta sẽ thu được kết quả bên dưới

  ![EC2](/images/3.backupresources/9_AIMCreated.png?width=90pc)