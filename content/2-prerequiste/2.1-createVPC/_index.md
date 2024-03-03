---
title : "Create VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---


In this step, we will need to create a VPC with one public/private subnet. This VPC will be used to deploy the development environment for our React Appliaction via the Cloud9 Service.

The architecture overview after completing this step will be as follows:

![VPC](/images/2-prerequiste/2.1-createVPC/001-createVPC.png)

We will utilize the **VPC and more** feature to quickly create the VPC.


In the **Create VPC** interface:

- Select the **VPC and more** feature.
- In the **Name tag auto-generation** section, check the box and enter: `workshop-01`.
- For IPv4 CIDR block, enter `10.10.0.0/16`.

![VPC](/images/2-prerequiste/2.1-createVPC/002-createVPC.png)

- In the **Number of Availability Zones (AZs)** section, choose 1.
- Next, for both **Number of public subnets** and **Number of private subnets**, select 1 each.

![VPC](/images/2-prerequiste/2.1-createVPC/003-createVPC.png)

- Then, toggle **Customize subnets CIDR blocks** and reconfigure the CIDR for the 2 subnets:
  - Public subnet: `10.10.1.0/24`
  - Private subnet: `10.10.2.0/24`
- For **NAT gateways** select: **None**
- Similarly, **VPC endpoints**, select: **None**
- Finally, click **Create VPC**

![VPC](/images/2-prerequiste/2.1-createVPC/004-createVPC.png)

{{% notice note%}}
**Why not create the NAT Gateway now?** The initial architecture diagram indeed includes a NAT Gateway. However, I will guide you on how to create it in the following section. We will understand the role of NAT in this model.

{{% /notice %}}

To learn how to manually create a VPC with public/private subnets, you can refer to the lab:
[Start with amazon VPC](https://000003.awsstudygroup.com/)