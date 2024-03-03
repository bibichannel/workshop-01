---
title : "Tạo ACM"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

Sử dụng AWS Certification Manager (ACM) để cung cấp, quản lý và triển khai các chứng chỉ SSL/TLS công khai và riêng tư để sử dụng với các dịch vụ AWS và tài nguyên. ACM loại bỏ quy trình mua, tải lên và gia hạn chứng chỉ SSL/TLS thủ công tốn nhiều thời gian.

- Truy cập console của ACM, chọn **Request certificate** và click **Next**.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/001-createACM.png)

- Ta cần yêu cầu chứng chỉ cho child domain `workshop-01.bibichannel.site`, nên ta điền vào phần **Fully qualified domain name**.
- Về **Validation method** ta nên sử dụng **DNS validation** để quá trình thẩm định nhanh hơn.
- Còn lại ta để mặc định.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/002-createACM.png)

- Chọn **Create** và ta đã tạo xong ACM, nhưng nó sẽ hiện status là **Pending validation**. Điều cần làm tiếp theo là ta cần tạo một record để quá trình thẩm định diễn ra thành công.
- Và vì các dịch vụ các dịch vụ AWS liên kết khá là khăng khít với nhau nên ta chỉ cần click vào **Create record in route 53**.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/003-createACM.png)

- Giao diện tạo record hiện ra, nó sẽ tạo ra một CNAME record để tiến hành validation cho domain của chúng ta.
- Click vào **Create records**

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/004-createACM.png)

- Tạo record thành công.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/005-createACM.png)

- Sau khi tạo xong record thì ACM cũng đã thẩm định thành công domain của chúng ta và giờ domain của chúng ta đã có chứng chỉ ssl/tls. Bạn có thể truy cập `https://workshop-01.bibichannel.site` để xem chứng chỉ.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/006-createACM.png)

