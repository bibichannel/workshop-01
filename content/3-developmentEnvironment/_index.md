---
title : "Connect to EC2 servers"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

Trong bước này chúng ta sẽ sử dụng Cloud9 service để tiến hành triển khai React App của chúng ta.

**AWS Cloud9**: là một môi trường phát triển tích hợp (IDE) cho phép bạn viết, chạy và gỡ lỗi mã của mình trên trình duyệt. Cloud9 bao gồm một trình soạn thảo mã, trình gỡ lỗi và giao diện dòng lệnh. Cloud9 được đóng gói sẵn với các công cụ cần thiết cho các ngôn ngữ lập trình phổ biến, bao gồm JavaScript, Python, PHP, v.v..

Và nó cho phép ta tạo một **Cloud9 no-ingress ec2 instance** để có thể tăng tính bảo mật cho quá trình phát triển ứng dụng web.
Nó bảo gồm việc tạo EC2 instance trong private subnet và dùng Session Manager để tiến hành connect từ Cloud9 vào EC2 instance của ta như sơ đồ dưới đây

![IMAGE](/images/3-developmentEnvironment/001-developmentEnvironment.png)

Với việc tạo EC2 instance cho dịch vụ Cloud9 trong private subnet và tạo các interface enpoint cho SSM là chuẩn sách giáo khoa rồi. 

Vậy ở đây ta cần thêm public subnet và NAT Gateway chi?

Đó là vì khi bạn triển khai môi trường development thì khi cài đặt các depedencies cho dự án của bạn thì bạn vẫn cần phải trên internet về. Và trong private subnet nếu ko được liên kết với NAT gateway được đặt trong public subnet thì không thể truy cập internet được.

Bạn có thể tham khảo thêm [ở đây](https://docs.aws.amazon.com/cloud9/latest/user-guide/vpc-settings.html#vpc-settings-create-subnet)

Theo mô hình trên ta sẽ cùng trải qua các bước sau đây trong phần này để phát triển ứng dụng và quản lý source code của chúng ta:

### Nội Dung
 - [Tạo Cloud9](3.1-createCloud9/)
 - [Tạo ElasticIP](3.2-createElasticIP/)
 - [Tạo NAT gateway](3.3-createNatGateway/)
 - [Tạo Routes cho Route Table](3.4-createRoutes/)
 - [Kiểm tra kết nối internet](3.5-checkConnectionInternet/)
 - [Tạo React App](3.6-createReactApp/)
 - [Đẩy code lên CodeCommit](3.7-pushCode/)
