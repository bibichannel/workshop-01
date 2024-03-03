---
title : "Phát triển và triển khai static website lên AWS Cloud"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

### Tổng quan

Cloud Computing hiện tại đang dần trở thành xu thế của thế giới. Rất nhiều công ty đang dần xây dựng, đưa cơ sở hạ tầng cùa mình lên cloud vì tính chất: nhanh chóng, sự đàn hồi, tiết kiệm chi phí, triển khai toàn cầu trong vòng vài phút.
- Và vì thế trong phần hướng dẫn này, mình sẽ hướng dẫn các bạn thực hiện triển khai quá trình phát triển ứng dụng react application của mình ngay trên cloud AWS nhờ công cụ Cloud9 IDE. 
- Tiếp đó là thực hiện tạo CI/CD cho dự án của chúng ta qua bộ công cụ Codepipeline.
- Và cuối cùng là phân phối nội dung website đến toàn cầu thông qua Cloudfront và quản lí tên miền của riêng ta thông qua Route 53.

Cùng xem diagram dưới đây để hình dung ra bức tranh toàn cảnh của bài lab này.

![IMAGE](/images/1-introduce/001-introduce.png)

### Nội dung
- [1. Giới thiệu](./1-introduce/)
- [2. Chuẩn bị](./2-prerequiste/)
- [3. Tạo môi trường phát triển](./3-developmentEnvironment/)
- [4. Triển khai CI/CD pipeline](./4-createCICD/)
- [5. Public webite](./5-publicWebsite&Distribution/)
- [6. Vô hiệu hoá Cache](./6-invalidateCacheCloudfront/)
- [7. Dọn dẹp tài nguyên](./7-cleanup/)
