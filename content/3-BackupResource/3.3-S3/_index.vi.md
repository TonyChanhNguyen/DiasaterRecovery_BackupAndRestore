---
title : "S3"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3 </b> "
---

### Tạo S3 UI bucket ở region thứ hai **Sydney (ap-southeast-2)**

 1 Click [S3](https://s3.console.aws.amazon.com/s3/buckets) để chuyển hướng đến trang chủ **S3**

 2 Sao chép tên của **UI bucket** ở region **Singapore (ap-southeast-1)**. Nó sẽ có định dạng ```backupandrestore-uibucket-xxxx```

 ![S3 Bucket](/images/3.backupresources/10_S3Bucket.png?width=90pc)

 3 Click nút ***Create bucket***

 ![S3 Bucket](/images/3.backupresources/11_S3BucketCreating.png?width=90pc)

 4 Nhập tên của bucket sử dụng cho **UI Bucket** mà bạn đã sao chép ở bước 2 và thêm "**-dr**" ở phía sau

 5 Chọn  **Sydney (ap-southeast-2)** ở mục **AWS Region**

  ![S3 Bucket](/images/3.backupresources/12_S3BucketCreating_1.png?width=90pc)

 6 Trong phần **Object Ownership**. Chọn **ACLs enabled**
 
  ![S3 Bucket](/images/3.backupresources/13_S3BucketCreating_2.png?width=90pc)

 7 Trong phần **Block Public Access settings for this bucket**. Bỏ chọn ở ô **Block *all* public access** bao gồm tất cả các phần tử con.
 Nhấn chọn ở ô **I acknowledge that the current settings….**

  ![S3 Bucket](/images/3.backupresources/14_S3BucketCreating_3.png?width=90pc)

 8 Nhấn chọn nút ***Create Bucket*** để khởi tạo **S3 Bucket**

  ![S3 Bucket](/images/3.backupresources/15_S3BucketCreating_4.png?width=90pc)

 9 Sau khi **S3 Bucket** được khởi tạo thành công, chúng ta sẽ nhận được kết quả bên dưới

  ![S3 Bucket](/images/3.backupresources/16_S3BucketCreated.png?width=90pc)