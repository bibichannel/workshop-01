---
title : "Tạo Cloudfront"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 5.3 </b> "
---

Trong bước này, chúng ta sẽ tạo Cloudfront để phần phối nội dung website của chúng ta.

- Truy cập vào console của Cloudfront, tại **Origin domain** ta chọn url của **workshop-01-react** s3 bucket.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/001-createCloudfront.png)

-Đối với quyền truy cập Origin, hãy chọn **Legacy access identities**. Đối với **Origin access identity**, bạn có thể chọn từ danh sách hoặc chọn **Create new OAI**.
- Tích chọn **Yes, update the bucket policy** tại phần **Bucket policy**.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/002-createCloudfront.png)

- Tại **Compress objects automatically** khi gửi nội dung đến viewer ta chọn **yes**
- **Viewer protocol policy** sẽ là **Redirect HTTP to HTTPS**.
- Còn lại giữ mặc định.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/003-createCloudfront.png)

- Cuộn xuống dưới tại **WAF**, trong bài lab này ta sẽ không sử dụng nó. **Chọn Do not enable security protections**
- Ta cũng sẽ không chọn phân phối nội dung của chúng ta toàn global mà chỉ giới hạn trong vài khu vực. Nên Price class chọn **Use North America, Europe, Asia, Middle East, and Africa**.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/004-createCloudfront.png)

- Tại **Alternate domain name (CNAME)** ta nhập child domain của ta: `workshop-01.bibichannel.site`
- **Custom SSL certificate** chọn ACM certificate ta đã tạo ở [bước 5.2](../5.2-createACM/).

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/005-createCloudfront.png)

- Ở **Default root object** ta nhập `index.html`.
- Sau đó ấn **Create distribution**.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/006-createCloudfront.png)

- Cloudfront của ta đã được tạo thành công với url sau: `https://d1y4dlqj807yu9.cloudfront.net`. Quá trình phân phối sẽ diễn ra trong khoảng thời gian ngắn trong vòng vài phút.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/007-createCloudfront.png)

- Ta truy cập vào thử thì thấy website đã hoạt động.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/008-createCloudfront.png)

- Nhưng khi ta truy cập vào `https://workshop-01.bibichannel.site`. THì thấy website của chúng ta chưa có.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/009-createCloudfront.png)

- Đây là do ta đã thiếu A record DNS của child domain trỏ đến url Cloudfront resources. Bước tiếp theo ta sẽ đi tạo record.