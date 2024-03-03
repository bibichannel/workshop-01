---
title : "Create Interface Enpoint"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

To allow other services to connect to EC2 instances located in private subnets via **Session Manager**, we need to place the System Manager's endpoint within the VPC, meaning using **VPC interface endpoints**. 

Therefore, in this instructional section, we will create the following 3 interfaces:
1. Service **com.amazonaws.<region>.ssm** named `Ssm`
2. Service **com.amazonaws.<region>.ec2messages** named `Ec2message`
3. Service **com.amazonaws.<region>.ssmmessages** named `Ssmmessage`

{{%notice note%}}
To create a VPC Endpoint, we need to enable the DNS hostnames feature on the VPC. Recall that we enabled this feature when creating the VPC initially. You can refer to more details [here](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-prerequisites.html).

{{%/notice%}}

Access the VPC service management interface, click on **Endpoint**, and then click on **Create Endpoint**.

![ENPOINT](/images/2-prerequiste/2.3-createInterface/001-createEndpoint.png)

On the Create endpoint page:
- In the  **Name tag** section, enter `Ssm`.
- For **Service category**, select: **AWS services**

![ENPOINT](/images/2-prerequiste/2.3-createInterface/002-createEndpoint.png)

- Next, **Service Name**, enter: `ssm` then select service name: **com.amazonaws.us-east-1.ssm**.
- Under VPC, select  **workshop-01-vpc**.
- hoose the first **AZ** and select  **private subnet**

![ENPOINT](/images/2-prerequiste/2.3-createInterface/003-createEndpoint.png)

Scroll down.
- In the **Security Group** section, select the **VPC Endpoint** security group we previously created.
- In the **Policy** section, choose **Full access**.

![ENPOINT](/images/2-prerequiste/2.3-createInterface/004-createEndpoint.png)

**Continue creating 2 more interface endpoints, and below is the result after completion.**

![ENPOINT](/images/2-prerequiste/2.3-createInterface/005-createEndpoint.png)

