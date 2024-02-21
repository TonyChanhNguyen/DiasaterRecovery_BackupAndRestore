---
title : "Cấu hình ứng dụng"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 6.3 </b> "
---

### EC2

1 Nhấn [EC2](https://ap-southeast-2.console.aws.amazon.com/ec2/home?region=ap-southeast-2) để chuyển hướng đến trang chủ trong region **Sydney - (ap-southeast-2)**

2 Chọn máy chủ **BackupAndRestoreSecondary**, sau đó nhấn nút ***Connect***

 ![Modify Application](../../../images/6.failovertosecondary/31_ModifyApp.png?width=90pc)

3 Chọn **Session Manager**, sau đó nhấn nút ***Connect***

 ![Modify Application](../../../images/6.failovertosecondary/32_ModifyApp.png?width=90pc)

4 Sau một lúc, một cửa sổ dòng lệnh sẽ xuất hiện

 ![Modify Application](../../../images/6.failovertosecondary/33_ModifyApp.png?width=90pc)

5 Hãy kết nối tới CSDL RDS ở region thứ hai **Sydney - (ap-southeast-2)**
```
sudo su ec2-user
cd /home/ec2-user
```
Thay thế **backupandrestore-secondary-region.xxxx.us-west-1.rds.amazonaws.com** với địa chỉ **Endpoint** đã được sao chép từ phần [RDS](../6.2-rds/)
```
sudo mysql -u UniShopAppV1User -P 3306 -pUniShopAppV1Password -h backupandrestore-secondary-region.xxxx.us-west-1.rds.amazonaws.com
```
Nhập **show databases**
```
show databases;
```
Bạn sẽ thấy kết quả như bên dưới:
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| unishop            |
+--------------------+
5 rows in set (0.02 sec)

```
Nhập **exit** để trở về cửa sổ dòng lệnh
```
MySQL [(none)]> exit

```

6 Mở tệp **unishopcfg.sh** để chỉnh sửa với **nano** hoặc **vi**

```
sudo nano unishopcfg.sh

```
7 Thay thế  **backupandrestore-secondary-region.xxxx.us-west-1.rds.amazonaws.com** bằng địa chỉ **Endpoint** mà bạn đã sao chép từ phần [RDS](../6.2-rds/). Thay đổi **AWS_DEFAULT_REGION** thành ```ap-southeast-2```. Thay đổi **UI_RANDOM_NAME** thành tên của **S3 Bucket** đã tạo ở region **Sydney - (ap-southeast-2)** (kết thúc bằng ký tự ```-dr```)

```
#!/bin/bash
export Database=backupandrestore-secondary-region.ctd11hzme0gz.ap-southeast-2.rds.amazonaws.com
export DB_ENDPOINT=backupandrestore-secondary-region.ctd11hzme0gz.ap-southeast-2.rds.amazonaws.com
export AWS_DEFAULT_REGION=ap-southeast-2
export UI_RANDOM_NAME=backupandrestore-uibucket-xbo9p0akmbgb-dr
```
Thoát và lưu lại thay đổi
{{% notice tip %}}
Sau khi chỉnh sửa xong, nhấn tổ hợp phím **"Ctrl + X" ->** **"Y" ->** **"Enter"** để lưu lại và thoát ra
 {{% /notice %}}

8 Hãy sử dụng câu lệnh **source** để đọc và thực thi các câu lệnh từ tệp **unishopcfg.sh**

```
source unishopcfg.sh
```

9 Hãy sao chép các tệp của ứng dụng đến **S3 bucket**

{{% notice note %}}
Nếu **S3 buckets** của chúng ta chứa dữ liệu ứng dụng thì chúng ta cần phải lên lịch sao lưu định kỳ để đạt được mục tiêu RPO. Điều này có thể được hoàn thành bởi **Cross Region Replication**. Bởi vì bucket của chúng ta không chứa dữ liệu, chỉ chứa code, chúng ta sẽ khôi phục các nội dung từ máy chủ EC2
 {{% /notice %}}

```
sudo aws s3 cp /home/ec2-user/UniShopUI s3://$UI_RANDOM_NAME/ --recursive --grants read=uri=http://acs.amazonaws.com/groups/global/AllUsers

```

10 Khởi động lại máy chủ EC2 để những thay đổi được áp dụng

```
sudo reboot
```

### Tạo tệp cấu hình ứng dụng

1 Sử dụng bất kỳ trình chỉnh sửa thông dụng nào, tạo một tệp mới với tên là ```config.json```. Đặt thông số **host** là **EC2 public IPv4 DNS name** đã được sao chép ở  phần [EC2](../6.1-ec2/), thêm  (‘http://') . Cuối cùng, đặt thông số **region** là **ap-southeast-2**

2 Cuối cùng, ```config.json``` sẽ có định dạng giống với mẫu này

```
{
    "host": "http://ec2-XXX-XXX-XXX-XXX.ap-southeast-2.compute.amazonaws.com",
    "region": "ap-southeast-2"
}
```

### S3

1 Nhấn [S3](https://s3.console.aws.amazon.com/s3/home?region=ap-southeast-2#) để chuyển hướng đến trang chủ

2 Nhấn chọn **backupandrestore-uibucket-xxxx-dr.**

 ![Modify Application](../../../images/6.failovertosecondary/34_ModifyApp.png?width=90pc)

3 Nhấn nút ***Upload***

 ![Modify Application](../../../images/6.failovertosecondary/35_ModifyApp.png?width=90pc)

4 Nhấn nút ***Add Files*** và chọn tệp **config.json**

 ![Modify Application](../../../images/6.failovertosecondary/36_ModifyApp.png?width=90pc)

5 Ở phần **Permissions Section**. Chọn ô **Specify Individual ACL permissions**. Chọn ô **Read** ở mục **Everyone (public access)**

 ![Modify Application](../../../images/6.failovertosecondary/37_ModifyApp.png?width=90pc)

6 Chọn ô **I understand the effects of these changes on the specified objects.**. Nhấn nút ***Upload***

 ![Modify Application](../../../images/6.failovertosecondary/38_ModifyApp.png?width=90pc)

Nhấn nút ***Close***

7 Nhấn chọn **Properties**. Ở phần **Static website hosting**, nhấn nút ***Edit***

 ![Modify Application](../../../images/6.failovertosecondary/39_ModifyApp.png?width=90pc)
 ![Modify Application](../../../images/6.failovertosecondary/40_ModifyApp.png?width=90pc)

8 Ở phần **Static website hosting** chọn ô **Enable**. Nhập ```index.html``` ở mục **Index document** và nhập ```error.html``` ở mục **Error Document**

 ![Modify Application](../../../images/6.failovertosecondary/41_ModifyApp.png?width=90pc)

9 Nhấn nút ***Save changes***

 ![Modify Application](../../../images/6.failovertosecondary/42_ModifyApp.png?width=90pc)

10 Ở phần **Static website hosting**. Nhấn chọn **Bucket website endpoint**

 ![Modify Application](../../../images/6.failovertosecondary/43_ModifyApp.png?width=90pc)
 ![Modify Application](../../../images/6.failovertosecondary/44_ModifyApp.png?width=90pc)

#### Chúc mừng! Bạn sẽ thấy ứng dụng của bạn The Unicorn Shop ở region ap-southeast-2

