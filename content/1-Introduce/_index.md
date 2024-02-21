---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

Sample application is Unishop. It is a Spring Boot Java Application connect to MySQL database with a frontend written by Bootstrap.
This application is launch in a EC2 Instance (t3.small) with a dedicated VPC using a Public Subnet. Note that this is not the ideal infrastructure architecture for running highly availability production applications but suffices for this workshop.

To configure a infrastructure and deploy the application, we will use Cloudformation. Cloudformation is an easy way to speed up cloud provisioning with infrastructure as code.

We will initially deploy Unishop to the ap-southeast-1 AWS Region and verify functionality. Then we will use an AWS EC2 AMI and AWS Backup for creating copies of application server and database in ap-southeast-2 region. Finally, we will use the copies for creating and testing a fully functional application in ap-southeast-2 region.
![Architecture](../images/Architecture.png?width=60pc)