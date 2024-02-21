---
title : "Sao lưu và phục hồi"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

# Sao lưu và phục hồi

### Tổng quan

Trong bài lab này, chúng ta sẽ triển khai ứng dụng trong một AWS Region và sau đó sử dụng AWS Backup và EC2 AMIs để tạo một bản backup của cửa hàng chúng ta ở một Region khác. Chúng ta sẽ khám phá DR bằng việc mô phỏng một thảm họa trong Region chính và phục hồi ứng dụng trong Region backup. Module này sẽ mất khoảng 90 phút để hoàn thành

### Nội dung

1. [Giới thiệu](1-introduce/)
2. [Các bước chuẩn bị](2-pre-requisites/)
3. [Sao lưu tài nguyên](3-backupresource/)
4. [Sao chép sang Region thứ hai](4-copytosecondregion/)
5. [Kiểm tra Website](5-verifywebsite/)
6. [Dự phòng sang Region thứ hai](6-failovertosecondary/)
7. [Dọn dẹp tài nguyên](7-cleanup/)