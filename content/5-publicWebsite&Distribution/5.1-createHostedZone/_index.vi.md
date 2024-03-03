---
title : "Tạo hosted zone"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 5.1 </b> "
---

Ở đây vì mình đang sở hữu domain name có tên là `bibichannel.site` ở domain registrar khác nên ở Route 53 mình sẽ tạo một hosted zone để quản lí tên miền con của mình.

Và tên miền con này sẽ được mình dùng để phân giải ra địa chỉ url resource của thằng Cloudfront ditribution.

- Truy cập vào Console Route 53 ta chọn **Hosted zones** sau đó click **Create hosted zone**

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/001-hostedZone.png)

- Ở **Domain name**, nhập `workshop-01.bibichannel.site` để tạo child domain cho **bibichannel.site**
- **Descriptions** nhập `The hosted zone used for workshop-01.bibichannel.site domain`
- **Type** ta sẽ chọn là **Public hosted zone**

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/002-hostedZone.png)

- Sau khi tạo xong ta sẽ thấy 2 record **NS** và **SOA** được tạo ra.
- **Record NS(Name Server)** sẽ chứa thông tin của name server của aws định tuyến các yêu cầu liên quan đến tên miền này.
- **Record SOA(Start of Authority)** trong AWS Route 53 là một bản ghi tài nguyên quan trọng trong hệ thống DNS, chứa thông tin quản lý về tên miền cụ thể. Bản ghi SOA thường được sử dụng để xác định máy chủ tên miền chính (primary name server) cho tên miền, cũng như các thông tin quản lý khác như Zone ID, địa chỉ email của administrator,...
- Xem thêm [tại đây](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/SOA-NSrecords.html).

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/003-hostedZone.png)

- Tiếp theo ta cần phải tạo các record NS tại domain registrar mà ta đã đăng ký tên miền trỏ về **Name server** của AWS.

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/004-hostedZone.png)

- Record NS này sẽ quyết định máy chủ nào sẽ quản lí thông tin của child domain của chúng ta. Và ở đây là AWS Route 53.