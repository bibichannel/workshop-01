---
title : "Create Routes"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

To create a Private Route Table and associate it with private subnets:

In the VPC interface:
- Select Route Tables.
- Choose the private route table.

![Image](/images/3-developmentEnvironment/3.4-createRoutes/001-createRoute.png)

In the private route table interface:
- Select **Edit routes**.
![Image](/images/3-developmentEnvironment/3.4-createRoutes/002-createRoute.png)

In the **Edit routes** interface:
- Add a new route with the destination to the internet.
- To route traffic to the internet, target the NAT gateway with the ID of the NAT gateway you just created.
- Then, save it.

![Image](/images/3-developmentEnvironment/3.4-createRoutes/003-createRoute.png)

Returning to the private route table interface, you will see that routes for routing traffic to the internet through the NAT gateway have been added.

![Image](/images/3-developmentEnvironment/3.4-createRoutes/004-createRoute.png)

