---
title : "Tạo record"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---

- Truy cập **Route 53**, phần **Hosted zones**, chọn **workshop-01.bibichannel.site**, rồi ấn tạo **record**.
- Ta chọn **Record type** là A và click bật **Alias**.

![IMAGE](/images/5-publicWebsite&Distribution/5.4-createRecord/001-createRecord.png)

- Ta chọn **Route traffic to** Cloudfront
- Rồi chọn url cloudfront distribution ta đã tạo ở [bước 5.3](../5.3-createCloudfront/).
- Nhấn **Create records**.

![IMAGE](/images/5-publicWebsite&Distribution/5.4-createRecord/002-createRecord.png)

- Quay lại đường dẫn `https://workshop-01.bibichannel.site`
- Ta thấy website của ta đã lên rồi. Quá trình này có thể tốn thời gian, bạn chịu khó đợi nhé.

![IMAGE](/images/5-publicWebsite&Distribution/5.4-createRecord/003-createRecord.png)