---
title : "Tạo NAT gateway"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

Truy cập vào VPC
- Chọn NAT Gateways
- Create NAT gateway

Trong giao diện **Create NAT gateway**
- Ta đặt tên như sau `workshop-01-ngw`
- **Subnet** ta chọn **public subnet**
- **Connectivity type** ta chọn **Public**
- **Elastic IP allocation ID** chọn EIP ta vừa mới tạo
- Chọn **Create NAT gateway**

![IMAGE](/images/3-developmentEnvironment/3.3-createNatGateway/001-createNAT.png)

Thành công tạo NAT gateway

![IMAGE](/images/3-developmentEnvironment/3.3-createNatGateway/002-createNAT.png)



