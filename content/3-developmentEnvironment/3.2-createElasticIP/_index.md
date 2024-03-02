---
title : "Create Elastic IP"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

Để tạo được NAT gateway ta cần phải tạo một Elastic IP public để gán vào NAT gateway.

Truy cập EC2
- Chọn **Elastic IPs**
- Chọn **Allocate Elastic IP address**

![IMAGE](/images/3-developmentEnvironment/3.2-createElasticIP/001-createEIP.png)

Trong giao diện Allocate Elastic IP address
- **Network border group** chọn đúng region bạn đang thực hành. Ở đây mình chọn **us-east-1** 
- **Public IPv4 address pool**, chọn **Amazon’s pool of IPv4 addresses**
- Chọn **Allocate**

![IMAGE](/images/3-developmentEnvironment/3.2-createElasticIP/002-createEIP.png)

Vậy là ta đã tạo thành công Elastic IP.

