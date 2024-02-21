---
title : "S3 Access"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

 1 Click [S3](https://console.aws.amazon.com/s3/home?region=ap-southeast-1#/) to nagative to dashboard **S3**

2 Click the **Block Public Access settings for this account** link

 ![Block Public Access](../../images/2.prerequisites/2_BlockPublicAccess.png?width=90pc)
  {{% notice info %}}
   If you can not find  **Block Public Access settings for this account** in **S3** dashboard, click the left conner of the screen
  ![Disable Block Public Access](../../images/2.prerequisites/1_Note.png?width=90pc)
 {{% /notice %}}

3 If you see  **Block all public access** is **On**, let's click ***Edit*** button

 ![Edit Block Public Access](../../images/2.prerequisites/3_1_BPA.png?width=90pc)

 {{% notice info %}}
  If you see  **Block all public access** is **Off**, you can skip steps below and begin [Primary Region](../2.2-primaryregion/)
  ![Disable Block Public Access](../../images/2.prerequisites/3_BPAD.png?width=90pc)
 {{% /notice %}}

4 Disable **Block Public Access settings for this account**  checkbox include children, then click ***Save change*** button for saving

 ![Disable Block Public Access](../../images/2.prerequisites/4_BPAEnable.png?width=90pc)

5 Enter ``confirm`` and click ***confirm*** button to confirm

 ![Confirm Editing Block Public Access](../../images/2.prerequisites/6_ConfirmBPA.png?width=90pc)

6 After that you will get the result same as below, **Block Public Access settings for this account** was **Disable**

 ![Result](../../images/2.prerequisites/7_Result.png?width=90pc)