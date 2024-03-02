---
title : "Create Security Group"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

Vì ta sẽ tạo Cloud9 no-ingress ec2 instance nên ta cần phải tạo Security group cho các interface enpoint của dịch vụ **Session Manager**. Các kết nối này sẽ được mã hoá TLS qua HTTPS nên ta cần phải tạo inbound rule cho phép mở port 443.

1. Truy cập giao diện quản trị dịch vụ VPC
- Click **Security Group**.
- Click **Create security group**.

![SG](/images/2-prerequiste/2.2-createSG/001-createSG.png)

2. Trong giao diện Create security group
- Tại mục **Security group name**, điền `VPC Endpoint`.
- Tại mục **Description**, điền `Allow traffic to the endpoint`.
- Tại mục VPC, click vào và chọn VPC bạn đã tạo cho bài lab này.

![SG](/images/2-prerequiste/2.2-createSG/002-createSG.png)

- Cấu hình **inbound rule** và **outbound rule** cho SG ta chọn như hình dưới.

![SG](/images/2-prerequiste/2.2-createSG/003-createSG.png)

{{% notice info %}}
Với inbound rule có source là CIDR của VPC cho phép các tài nguyên nằm trong VPC có thể gửi traffic tới security group này.

{{% /notice %}}

- Ta click **Create security group**

