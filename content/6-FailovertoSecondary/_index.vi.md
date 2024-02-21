---
title : "Dự phòng sang Region thứ hai"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---

Khi một sự kiện dịch vụ thuộc khu vực ảnh hướng đến ứng dụng Unicorn ở region chính **Singapore (ap-southeast-1)**, chúng ta muốn khai thác tài nguyên trong region thứ hai **Sydney (ap-southeast-2)**

Hãy tưởng tượng một sự kiện dịch vụ thuộc khu vực vừa xảy ra. Trong trường hợp này, chúng ta sẽ thực hiện một loạt các tác vụ để khai thác tài nguyên trong region thứ hai  **Sydney (ap-southeast-2)** một cách thủ công. Trong một môi trường sản phẩm, chúng ta sẽ tự động hóa những bước này bằng việc sử dụng một **AWS Cloudformation template** hoặc công cụ của bên thứ ba.

Chúng ta sẽ thực hiện:
 - Triển khai một máy chủ EC2 từ AMI (Amazon Machine Image)
 - Khôi phục cơ sở dữ liêu RDS từ bản sao lưu
 - Cấu hình ứng dụng

### Mô phỏng một sự kiện dịch vụ thuộc khu vực
Chúng ta sẽ mô phỏng một sự kiện dịch vụ thuộc khu vực ảnh hưởng đến website tĩnh S3 (S3 static website) trong region **Singapore (ap-southeast-1)** mà website The Unicorn Shop đang chạy

1 Nhấn [S3](https://s3.console.aws.amazon.com/s3/home?region=ap-southeast-1#) để chuyển hướng đến trang chủ

2 Nhấn vào bucket **backupandrestore-uibucket-xxxx**
   ![Failover to Secondary](../../images/6.failovertosecondary/1_S3Bucket.png?width=90pc)
3 Nhấn vào **Permissions**. Trong phần **Block public access (bucket settings)**, nhấn nút ***Edit***
   ![Failover to Secondary](../../images/6.failovertosecondary/2_S3Bucket.png?width=90pc)
4 Chọn ô **Block all public access**, sau đó nhấn nút ***Save*** để lưu
   ![Failover to Secondary](../../images/6.failovertosecondary/3_S3Bucket.png?width=90pc)
5 Nhập ```confirm```, sau đó nhấn nút ***Confirm***
   ![Failover to Secondary](../../images/6.failovertosecondary/4_S3Bucket.png?width=90pc)
6 Nhấn chọn **Properties**
   ![Failover to Secondary](../../images/6.failovertosecondary/5_S3Bucket.png?width=90pc)
7 Trong phần **Static website hosting**, nhấp vào đường dẫn **Bucket website endpoint**
   ![Failover to Secondary](../../images/6.failovertosecondary/6_S3Bucket.png?width=90pc)
8 Bạn sẽ thấy lỗi **403 Forbidden**
   ![Failover to Secondary](../../images/6.failovertosecondary/7_S3Bucket.png?width=90pc)

