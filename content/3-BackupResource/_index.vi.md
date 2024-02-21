---
title : "Sao lưu tài nguyên"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

Bây giờ chúng ta sẽ bắt đầu sao lưu các tài nguyên

Chúng ta sẽ thực hiện như sau:
 - Sao lưu cơ sở dữ liệu RDS
 - Tạo một EC2 AMI (Amazon Machine Image)
 - Tạo một S3 UI bucket mới

Chúng ta sẽ tạo một [backup plan](https://docs.aws.amazon.com/aws-backup/latest/devguide/creating-a-backup-plan.html) cho một sản phẩm ứng dụng và lên kế hoạch sao lưu định kỳ để đạt được mục tiêu RPO.

Tuy nhiên, ở bài lab này, chúng ta sẽ tạo một **manual backup** (Sao lưu thủ công)
