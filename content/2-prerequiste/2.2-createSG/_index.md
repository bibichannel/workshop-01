---
title : "Create Security Group"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

As we will be creating a Cloud9 no-ingress EC2 instance, we need to create a **Security Group** for the **Session Manager** service's endpoint interfaces. These connections will be encrypted via TLS over HTTPS, so we need to create an inbound rule to allow port 443.

1. Access the VPC service management interface:
- Click on **Security Groups**.
- Click on **Create security group**.

![SG](/images/2-prerequiste/2.2-createSG/001-createSG.png)

2. In the Create security group interface:
- In the **Security group name** field, enter `VPC Endpoint`.
- In the **Description** field, enter `Allow traffic to the endpoint`..
- Under VPC, click and select the VPC you have created for this lab.

![SG](/images/2-prerequiste/2.2-createSG/002-createSG.png)

- Configure the **inbound rule** and **outbound rule** for the SG as shown below.

![SG](/images/2-prerequiste/2.2-createSG/003-createSG.png)

{{% notice note%}}
For the inbound rule with the source CIDR of the VPC, it allows resources within the VPC to send traffic to this security group.

{{% /notice %}}

- Click on **Create security group**

