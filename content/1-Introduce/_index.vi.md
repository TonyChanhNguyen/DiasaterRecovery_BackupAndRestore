---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

Ứng dụng mẫu là Unishop. Nó là một ứng dụng Spring Boot Java kết nối tới một CSDL MySQL với một frontend được viết bằng Bootstrap.
Ứng dụng này được triển khai trên một EC2 Instance (t3.small) với một VPC chuyên dụng sử dụng một Public Subnet. Lưu ý rằng đây không phải là một kiến trúc cơ sở hạ tầng lý tưởng để chạy sản phẩm ứng dụng sẵn sàng cao nhưng đủ đáp ứng cho bài thực hành này.

Để cấu hình một hạ tầng và triển khai một ứng dụng, chúng ta sẽ sử dụng Cloudformation. Cloudformation là một cách thức dễ dàng để tăng tốc việc cung cấp cloud với hạ tầng là mã code (Infrastructure as Code - IaC).

Chúng ta sẽ bắt đầu triển khai Unishop đến ap-southeast-1 AWS Region và xác định chức năng. Sau đó sử dụng một EC2 AMI và AWS Backup để tạo những bản sao của máy chủ ứng dụng và cơ sở dữ liệu đến ap-southeast-2 region. Cuối cùng, chúng ta sẽ sử dụng các bản sao để tạo và kiểm tra một ứng dụng đầy đủ chức năng trong ap-southeast-2 region.

![Mô hình kiến trúc](../../images/Architecture.png?width=60pc)