---
title : "Tạo CodeCommit"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 2.5 </b> "
---

Chúng ta cần một nơi có thể lưu trữ source code của chúng ta mỗi khi phát triển một ứng dụng và cùng với đó là chúng ta cần phải bảo mật source code của chúng ta.

Với github, bitbucket, gitlab,... là các repo công cộng tuy có cung cấp cho ta các gói lưu trữ source code riêng tư nhưng đòi hỏi phải trả phí và các hợp đồng rằng buộc cũng như không chắc chắn server của họ không có downtime.

Trong khi đó aws cung cấp cho ta một dịch vụ có lưu trữ repository riêng tư là CodeCommit, nó tích hợp tốt với các dịch vụ aws khác cùng với khả năng bảo mật và quản lý quyền truy cập thông qua **IAM**.

Tất cả những lý do trên đều thuyết phục ta nên sử dụng CodeCommit. Và trong phần này chúng ta sẽ cùng tạo dịch vụ trên.

1. Đầu tiên. chúng ta sẽ tạo một repository codecommit.
- Truy cập vào CodeCommit
- Nhập tên của dự án ta muốn lưu trữ: `workshop-01-react`
- Phần miêu tả ta điền: `Repository for react application`
- Click vào **Create**

![VPC](/images/2-prerequiste/2.5-createCodeCommit/001-createCodeCommit.png)

Việc tạo một repo trên CodeCommit khá là đơn giản và nhanh chóng. Chỉ vài bước ta đã có một **repository private** cho dự án của chúng ta.

![VPC](/images/2-prerequiste/2.5-createCodeCommit/002-createCodeCommit.png)