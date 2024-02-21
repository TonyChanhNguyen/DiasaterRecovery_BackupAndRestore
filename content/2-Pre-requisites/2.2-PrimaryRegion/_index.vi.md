---
title : "Region chính"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Triển khai một Amazon CloudFormation Template

1 Tạo ứng dụng trên Region chính **Singapore (ap-southeast-1)** bằng việc khởi chạy [**CloudFormation Template**](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks/create/template?stackName=BackupAndRestore&templateURL=https://ee-assets-prod-us-east-1.s3.amazonaws.com/modules/630039b9022d4b46bb6cbad2e3899733/v1/BackupAndRestore.yaml) này

2 Nhấn nút ***Next*** 

 ![Cloudformation Template](../../../images/2.prerequisites/8_CloudformationTemplate.png?width=90pc)

3 Nhấn nút ***Next*** 

{{% notice info %}} 
Để LatestAmiId ở giá trị mặc định
{{% /notice  %}}

  ![Cloudformation Template](../../../images/2.prerequisites/9_CloudformationTemplate_1.png?width=90pc)

4 Nhấn nút ***Next*** 

 ![Cloudformation Template](../../../images/2.prerequisites/10_CloudformationTemplate_2.png?width=90pc)

5 Cuộn xuống phần cuối của trang, bật chọn ô **I acknowledge that AWS CloudFormation might create IAM resources with custom names**, sau đó nhấn nút ***Create stack***

  ![Cloudformation Template](../../../images/2.prerequisites/11_CloudformationTemplate_3.png?width=90pc)

6 **Cloudformation** đang tạo những tài nguyên cần thiết

 ![Cloudformation Template](../../../images/2.prerequisites/12_CloudformationTemplate_4.png?width=90pc)

{{% notice note %}} 
Qúa trình này mất ít nhất 15 phút để hoàn thành
{{% /notice %}}

7 Sau khi hoàn thành sẽ nhận được kết quả bên dưới

 ![Cloudformation Template](../../../images/2.prerequisites/13_CloudformationTemplate_Result.png?width=90pc)

8 Để kiểm tra ứng dụng đã đươc triển khai, truy cập [S3](https://console.aws.amazon.com/s3/home?region=ap-southeast-1#/) ở mục **Bucket** chúng ta sẽ thấy một Bucket có định dạng ```backupandrestore-uibucket-xxxx```

 ![Application Result](../../../images/2.prerequisites/14_ApplicationResult_1_1.png?width=90pc)

9 Nhấn chọn Bucketvừa mới tạo, cuộn xuống phần cuối cùng của mục **Permission**. Sao chép **Bucket website endpoint** của **S3 Bucket** vừa tạo

 ![Application Result](../../../images/2.prerequisites/15_ApplicationResult_2.png?width=90pc)

 ![Application Result](../../../images/2.prerequisites/16_ApplicationResult_3.png?width=90pc)

10 Nhập địa chỉ vừa tạo vào bất kỳ trình duyệt web nào và truy cập. Sau đó sẽ nhận được kết quả bên dưới, ứng dụng **The Unicorn Shop** đã được tạo tại Region **Singapore (ap-southeast-1)**

 ![Application Result](../../../images/2.prerequisites/17_ApplicationResult_4.png?width=90pc)