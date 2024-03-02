---
title : "Tạo VPC"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, chúng ta sẽ cần tạo một VPC có 2 subnet public / private.
VPC này sẽ được dùng để triển khai môi trường development cho React App của chúng ta thông qua Cloud9 Service.

Tổng quan kiến trúc sau khi các bạn hoàn tất bước này sẽ như sau:

![VPC](images\2-prerequiste\2.1-createVPC\001-networkVPC.png)

Ta sẽ sử dụng tính năng **VPC and more** để tiến hành tạo nhanh VPC.

1. Trong giao diện **Create VPC**

- Chọn tính năng **VPC and more**
- Phần **Name tag auto-generation** ta tích chọn và tiến hành nhập: `workshop-01`
- IPv4 CIDR block, nhập 10.0.0.0/16


![VPC](/images/arc-01.png)

Để tìm hiểu cách tạo VPC thủ công với public/private subnet các bạn có thể tham khảo bài lab :
  - [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)