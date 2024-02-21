---
title : "Truy cập S3"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

1 Click [S3](https://console.aws.amazon.com/s3/home?region=ap-southeast-1#/) để chuyển hướng đến trang chủ **S3**

2 Click vào mục **Block Public Access settings for this account**

 ![Block Public Access](../../../images/2.prerequisites/2_BlockPublicAccess.png?width=90pc)
  {{% notice info %}}
   Nếu không tìm thấy mục **Block Public Access settings for this account** ở trang chủ **S3**, nhấn chọn ở góc bên trái màn hình
  ![Disable Block Public Access](../../../images/2.prerequisites/1_Note.png?width=90pc)
 {{% /notice %}}

3 Nếu bạn thấy rằng **Block all public access** đang ở chế độ **On**, thì hãy bấm nút ***Edit***

 ![Edit Block Public Access](../../../images/2.prerequisites/3_1_BPA.png?width=90pc)

 {{% notice info %}}
  Nếu bạn thấy rằng **Block all public access** đang ở chế độ **Off**, bạn có thể bỏ qua các bước phía dưới và bắt đầu phần [Region chính](../2.2-primaryregion/)
  ![Disable Block Public Access](../../../images/2.prerequisites/3_BPAD.png?width=90pc)
 {{% /notice %}}

4 Tắt chọn ô **Block Public Access settings for this account** bao gồm cả các ô nhỏ, sau đó bấm ***Save change*** để lưu

 ![Disable Block Public Access](../../../images/2.prerequisites/4_BPAEnable.png?width=90pc)

5 Nhập ``confirm`` và nhấn nút ***confirm*** để xác nhận

 ![Confirm Editing Block Public Access](../../../images/2.prerequisites/6_ConfirmBPA.png?width=90pc)

6 Sau đó sẽ nhận được kết quả bên dưới, các **Block Public Access settings for this account** đã **Disable**

 ![Result](../../../images/2.prerequisites/7_Result.png?width=90pc)
