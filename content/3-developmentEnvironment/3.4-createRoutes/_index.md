---
title : "Create Routes for private route table"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

Tạo Route table - Private và stick vào các private subnet.

Trong giao diện VPC
- Chọn Route Tables
- Chọn **private route table**

![Image](/images/3-developmentEnvironment/3.4-createRoutes/001-createRoute.png)

Trong giao diện Route table private
- Ta chọn **Edit routes**

![Image](/images/3-developmentEnvironment/3.4-createRoutes/002-createRoute.png)

Trong giao diện edit routes
- Ta add thêm route mới với Destionation là ra internet
- Muốn ra internet ta sẽ target vào NAT gateway với ID là NAT gateway ta vừa mới tạo
- Sau đó ta save nó lại

![Image](/images/3-developmentEnvironment/3.4-createRoutes/003-createRoute.png)

Quay lại giao diện Route table private ta thấy
- Routes định tuyến traffic ra internet thông qua NAT gateway đã được thêm vào.

![Image](/images/3-developmentEnvironment/3.4-createRoutes/004-createRoute.png)

