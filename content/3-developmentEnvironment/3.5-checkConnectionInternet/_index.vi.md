---
title : "Kiểm tra kết nối Internet"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---

Sau khi ta hoàn đã đả thông internet cho EC2 trong private subnet kết nối ra ngoài internet. Ta quay lại giao diện của Cloud9 IDE tiến hành:
- `curl google.com`

![IMAGE](/images/3-developmentEnvironment/3.5-checkConnectionInternet/001-checkInternet.png)

- `ping 8.8.8.8`

![IMAGE](/images/3-developmentEnvironment/3.5-checkConnectionInternet/002-checkInternet.png)

Như ta đã thấy Ec2 đã connect internet thành công.