---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

### Sao chép EC2 AMI (Amazon Machine Image)

1 Nhấn [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=ap-southeast-1#/) để chuyển hướng đến trang chủ ở region **Singapore (ap-southeast-1)**

2 Chọn **AMIs**

3 Xác nhận trạng thái của bản sao lưu **BackupAndRestoreImage** là **Available**
  ![Copy AMI](../../../images/4.copytosecondregion/8_AIMCopy_1.png?width=90pc)
4 Chọn **BackupAndRestoreImage**. Click **Copy AMI** ở mục **Actions**
  ![Copy AMI](../../../images/4.copytosecondregion/9_AIMCopy_2.png?width=90pc)
5 Chọn **Sydney (ap-southeast-2** ở mục **Destination region**, sau đó nhấn nút ***Copy AMI***
  ![Copy AMI](../../../images/4.copytosecondregion/10_AIMCopy_3.png?width=90pc)
6 Quá trình sao chép **EC2 AMI** sẽ được khởi tạo
  ![Copy AMI](../../../images/4.copytosecondregion/11_AIMCopy_4.png?width=90pc)
7 Để kiểm tra kết quả, ta thực hiện:
 - Chuyển hướng đến [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=ap-southeast-2#/) ở region **Sydney (ap-southeast-2)**
 - Chọn **AMIs** và kiểm tra AMI vừa được sao chép sang từ region **Singapore (ap-southeast-1)**
   ![Copy AMI](../../../images/4.copytosecondregion/12_AIMCopy_5.png?width=90pc)