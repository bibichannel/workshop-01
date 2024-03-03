---
title : "Tạo Interface Enpoint"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

Để các dịch vụ khác thông qua **session manager** connect tới ec2 instace nằm trong private subnet ta phải đưa endpoint của System Manager vào trong VPC, nghĩa là sử dụng **VPC interface endpoint**:
Vì thế trong phần hướng dẫn này chúng ta sẽ tạo 3 interface sau:
1. Service **com.amazonaws.<region>.ssm** với tên `Ssm`
2. Service **com.amazonaws.<region>.ec2messages** với tên `Ec2message`
3. Service **com.amazonaws.<region>.ssmmessages** với tên `Ssmmessage`

{{%notice note%}}
Để tạo được VPC Endpoint chúng ta sẽ cần bật tính năng DNS hostnames trên VPC. Nhớ lại một chút lúc ban đầu chúng ta tạo VPC đã tích enable tính năng này rồi.
Bạn có thể tham khảo thêm [tại đây](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-prerequisites.html)

{{%/notice%}}

Truy cập đến giao diện quản trị của dịch vụ VPC click **Endpoint**, sau đó click **Create Endpoint**.

![ENPOINT](/images/2-prerequiste/2.3-createInterface/001-createEndpoint.png)

Ở trang Create endpoint.
- Ở phần **Name tag** ta điền `Ssm`.
- Ở phần **Service category** chọn: AWS services

![ENPOINT](/images/2-prerequiste/2.3-createInterface/002-createEndpoint.png)

- Tiếp theo **Service Name** nhập: `ssm` sau đó chọn service name: **com.amazonaws.us-east-1.ssm**.
- Tại mục VPC, chọn **workshop-01-vpc**.
- Chọn AZ đầu tiên và chọn **private subnet**

![ENPOINT](/images/2-prerequiste/2.3-createInterface/003-createEndpoint.png)

Kéo chuột xuống dưới.
- Tại mục **Security Group**, chọn security group **VPC Endpoint** mà chúng ta đã tạo trước đó.
- Tại mục **Policy**, chọn **Full access**

![ENPOINT](/images/2-prerequiste/2.3-createInterface/004-createEndpoint.png)

**Tiếp tục tạo thêm 2 interface enpoint nữa và dưới đây là kết quả sau khi ta đã tạo xong.**

![ENPOINT](/images/2-prerequiste/2.3-createInterface/005-createEndpoint.png)