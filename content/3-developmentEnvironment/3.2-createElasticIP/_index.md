---
title : "Create Elastic IP"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

To create a NAT gateway, we need to allocate a public Elastic IP to assign to the NAT gateway.

Access  EC2
- Select **Elastic IPs**.
- Click on **Allocate Elastic IP address**.

![IMAGE](/images/3-developmentEnvironment/3.2-createElasticIP/001-createEIP.png)

In the Allocate Elastic IP address interface:
- For **Network border group**, choose the correct region you are practicing in. Here, I select **us-east-1**.
- For P**ublic IPv4 address pool**, select **Amazon’s pool of IPv4 addresses**.
- Click **Allocate**

![IMAGE](/images/3-developmentEnvironment/3.2-createElasticIP/002-createEIP.png)

Now, you have successfully created an Elastic IP.

