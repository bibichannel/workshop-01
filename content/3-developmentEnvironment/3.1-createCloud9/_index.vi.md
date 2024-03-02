---
title : "Tạo Cloud9"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1 </b> "
---


1. Tại trang chủ của dịch vụ Clou9 ta click **Create environment**

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/001-createCloud9.png)

2. Ở phần **Details**
- Điền **Name** ta nhập `react-app-workshop`
- **Environment type** ta chọn **New EC2 instance**

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/002-createCloud9.png)

3. Ở phần **New EC2 instance** 
- Ta chọn loại instance **t3.small**
- Với **Platform** ta chọn **Amazon linux 2**
- **Timeout** ta để mặc định 30' khi không truy cập sẽ hibernate

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/003-createCloud9.png)

3. Phần network
- Phần **Network settings** với Connection ta chọn **AWS Systems Manager (SSM)**
- VPC Setting ta chọn **workshop-01-vpc** và **private subnet**
- Click **Create Cloud9**

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/004-createCloud9.png)

4. Kiểm tra tạo thành công hay không
Sau một khoảng thời gian tầm 10 - 30 phút ta đã tạo thành công Cloud9

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/005-createCloud9.png)

5. Truy cập vào Cloud9
Ta click vào Open Cloud9 IDE và truy cập vào giao diện của nó ta thấy bố cục cũng tương tự với các phần mềm IDE khác trên thị trường.

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/006-createCloud9.png)

Ta sẽ thực hiện ping 8.8.8.8 xem có thông internet không. Thì ta thấy tất cả các gói gửi đi đều bị loss. Điều này chứng tỏ môi trường phát triển của chúng ta không thể đi ra ngoài internet. 

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/007-createCloud9.png)

Như mình đã nói ở trên chúng ta sẽ không thể cài đặt các depedencies cần thiết cho dự án của chúng ta được nên bước tiếp theo ta cần phải làm nó thông ra internet thông qua việc tạo NAT gateway.
