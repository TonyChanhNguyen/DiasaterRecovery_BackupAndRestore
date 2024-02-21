---
title : "Modify Application"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 6.3 </b> "
---

### EC2

1 Click [EC2](https://ap-southeast-2.console.aws.amazon.com/ec2/home?region=ap-southeast-2) to navigate to the dashboard in **Sydney - (ap-southeast-2)** region

2 Select **BackupAndRestoreSecondary** instance, then click ***Connect*** button

 ![Modify Application](../../images/6.failovertosecondary/31_ModifyApp.png?width=90pc)

3 Click **Session Manager**, then click ***Connect*** button

 ![Modify Application](../../images/6.failovertosecondary/32_ModifyApp.png?width=90pc)

4 After a second, a terminal will appear

 ![Modify Application](../../images/6.failovertosecondary/33_ModifyApp.png?width=90pc)

5 Let's connect to RDS database in secondary reggion **Sydney - (ap-southeast-2)**
```
sudo su ec2-user
cd /home/ec2-user
```
Replace **backupandrestore-secondary-region.xxxx.us-west-1.rds.amazonaws.com** with **Endpoint** address which was copied at [RDS](../6.2-rds/) section
```
sudo mysql -u UniShopAppV1User -P 3306 -pUniShopAppV1Password -h backupandrestore-secondary-region.xxxx.us-west-1.rds.amazonaws.com
```
Enter **show databases**
```
show databases;
```
You will see the results same as below:
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
Enter **exit** to come back to the terminal
```
MySQL [(none)]> exit

```

6 Open **unishopcfg.sh** file to edit by **nano** or **vi**

```
sudo nano unishopcfg.sh

```
7 Replace  **backupandrestore-secondary-region.xxxx.us-west-1.rds.amazonaws.com** by **Endpoint** address you copied at [RDS](../6.2-rds/) section. Replace **AWS_DEFAULT_REGION** into ```ap-southeast-2```. Replace **UI_RANDOM_NAME** into name of **S3 Bucket** created in **Sydney - (ap-southeast-2)** region (end by ```-dr```)

```
#!/bin/bash
export Database=backupandrestore-secondary-region.ctd11hzme0gz.ap-southeast-2.rds.amazonaws.com
export DB_ENDPOINT=backupandrestore-secondary-region.ctd11hzme0gz.ap-southeast-2.rds.amazonaws.com
export AWS_DEFAULT_REGION=ap-southeast-2
export UI_RANDOM_NAME=backupandrestore-uibucket-xbo9p0akmbgb-dr
```
Exit and save the changes
{{% notice tip %}}
After finishing, enter **"Ctrl + X" ->** **"Y" ->** **"Enter"** to save and exit
 {{% /notice %}}

8 Let's use the **source** command to read and execute commands from **unishopcfg.sh** file

```
source unishopcfg.sh
```

9 Let's copy the application files to the **S3 bucket**

{{% notice note %}}
If our **S3 buckets** contain application data then it would be necessary to schedule recurring backups to meet the target RPO. This could be done with **Cross Region Replication**. Since our bucket do not contain data, only code, we will restore the contents from the EC2 instance.
 {{% /notice %}}

```
sudo aws s3 cp /home/ec2-user/UniShopUI s3://$UI_RANDOM_NAME/ --recursive --grants read=uri=http://acs.amazonaws.com/groups/global/AllUsers

```

10 Restart the EC2 instance to apply changes

```
sudo reboot
```

### Create application configuration file

1 Using any editor, Create a new file name ```config.json```. Set the **host** property is **EC2 public IPv4 DNS name** copied at [EC2](../6.1-ec2/) section, add  (‘http://') . Finally, set the **region** property is **ap-southeast-2**

2 Finally, ```config.json``` should look similar to this example.

```
{
    "host": "http://ec2-XXX-XXX-XXX-XXX.ap-southeast-2.compute.amazonaws.com",
    "region": "ap-southeast-2"
}
```

### S3

1 Click [S3](https://s3.console.aws.amazon.com/s3/home?region=ap-southeast-2#) to navigate to the dashboard

2 Select **backupandrestore-uibucket-xxxx-dr.**

 ![Modify Application](../../images/6.failovertosecondary/34_ModifyApp.png?width=90pc)

3 Click ***Upload*** button

 ![Modify Application](../../images/6.failovertosecondary/35_ModifyApp.png?width=90pc)

4 Click ***Add Files*** button and chose **config.json** file

 ![Modify Application](../../images/6.failovertosecondary/36_ModifyApp.png?width=90pc)

5 At **Permissions Section**. Enable **Specify Individual ACL permissions** checkbox. Enable **Read** as the **Everyone (public access)**

 ![Modify Application](../../images/6.failovertosecondary/37_ModifyApp.png?width=90pc)

6 Enable **I understand the effects of these changes on the specified objects.** checkbox. Click ***Upload*** button

 ![Modify Application](../../images/6.failovertosecondary/38_ModifyApp.png?width=90pc)

Click ***Close*** button

7 Click **Properties**. At **Static website hosting**, Click ***Edit*** button

 ![Modify Application](../../images/6.failovertosecondary/39_ModifyApp.png?width=90pc)
 ![Modify Application](../../images/6.failovertosecondary/40_ModifyApp.png?width=90pc)

8 At **Static website hosting** click **Enable**. Enter ```index.html``` as the **Index document** and enter ```error.html``` as the **Error Document**

 ![Modify Application](../../images/6.failovertosecondary/41_ModifyApp.png?width=90pc)

9 Click ***Save changes*** button

 ![Modify Application](../../images/6.failovertosecondary/42_ModifyApp.png?width=90pc)

10 At **Static website hosting**. Click **Bucket website endpoint**

 ![Modify Application](../../images/6.failovertosecondary/43_ModifyApp.png?width=90pc)
 ![Modify Application](../../images/6.failovertosecondary/44_ModifyApp.png?width=90pc)

#### Congratulation! You will see your The Unicorn Shop application in ap-southeast-2 region



