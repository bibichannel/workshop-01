---
title : "Create NAT gateway"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

Access the VPC:
- Select **NAT Gateways**.
- Click on **Create NAT gateway**

In the **Create NAT gateway** interface:
- Name it as follows: `workshop-01-ngw`
- For **Subnet**, choose the **public subnet**.
- For **Connectivity type**, select **Public**.
- For **Elastic IP allocation ID**, choose the **Elastic IP** you just created.
- Click **Create NAT gateway**.

![IMAGE](/images/3-developmentEnvironment/3.3-createNatGateway/001-createNAT.png)

You have successfully created the **NAT gateway**.

![IMAGE](/images/3-developmentEnvironment/3.3-createNatGateway/002-createNAT.png)

