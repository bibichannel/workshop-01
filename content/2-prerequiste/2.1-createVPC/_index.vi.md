---
title : "Tạo VPC"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, chúng ta sẽ cần tạo một VPC có 1 public/private subnet.
VPC này sẽ được dùng để triển khai môi trường development cho React App của chúng ta thông qua Cloud9 Service.

Tổng quan kiến trúc sau khi các bạn hoàn tất bước này sẽ như sau:

![VPC](/images/2-prerequiste/2.1-createVPC/001-createVPC.png)

Ta sẽ sử dụng tính năng **VPC and more** để tiến hành tạo nhanh VPC.

Trong giao diện **Create VPC**

- Chọn tính năng **VPC and more**
- Phần **Name tag auto-generation** ta tích chọn và tiến hành nhập: `workshop-01`
- **IPv4 CIDR block**, nhập `10.10.0.0/16`

![VPC](/images/2-prerequiste/2.1-createVPC/002-createVPC.png)

- Ở phần **Number of Availability Zones (AZs)** ta chọn 1
- Tiếp đó **Number of public subnets** và **Number of private subnets** ta đều chọn 1

![VPC](/images/2-prerequiste/2.1-createVPC/003-createVPC.png)

- Tiếp toggle **Customize subnets CIDR blocks** ta tiến hành cấu hình lại CIDR cho 2 subet:
  - Public subnet: `10.10.1.0/24`
  - Private subnet: `10.10.2.0/24`
- **NAT gateways** ta sẽ chọn: **None**
- **VPC endpoints** ta cũng sẽ chọn: **None**
- Sau đó ta **Create VPC**

![VPC](/images/2-prerequiste/2.1-createVPC/004-createVPC.png)

{{% notice info %}}
**Tại sao không tạo luôn NAT Gateway?**. Trên diagram kiến trúc ban đầu đúng là có NAT Gateway. Nhưng mình sẽ hướng dẫn bạn tạo nó ở phần sau. Khi chúng ta biết rằng NAT sẽ có vai trò gì trong mô hình này.

{{% /notice %}}

Để tìm hiểu cách tạo VPC thủ công với public/private subnet các bạn có thể tham khảo bài lab :
[Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)