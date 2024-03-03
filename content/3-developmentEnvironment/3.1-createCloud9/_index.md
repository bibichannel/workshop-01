---
title : "Create Cloud9"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

1. TOn the homepage of the Cloud9 service, click **Create environment**.

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/001-createCloud9.png)

2. In the **Details** section
- Enter  **Name** as `react-app-workshop`.
- Choose **Environment type** as **New EC2 instance**.

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/002-createCloud9.png)

3. In the **New EC2 instance** section:
- Select instance type **t3.small**
- For **Platform** choose **Amazon linux 2**
- Leave **Timeout** as default (30 minutes before hibernation due to inactivity).

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/003-createCloud9.png)

3. Network section:
- Under **Network settings**, choose **AWS Systems Manager (SSM)** for Connection.
- For VPC Setting, select **workshop-01-vpc** and **private subnet**.
- Click **Create Cloud9**

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/004-createCloud9.png)

4. Check for successful creation:
After approximately 10-30 minutes, the Cloud9 environment should be successfully created.

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/005-createCloud9.png)

5. Access Cloud9:
Click on Open Cloud9 IDE to access its interface, which resembles other IDE software on the market.

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/006-createCloud9.png)

You can perform a ping to 8.8.8.8 to check internet connectivity. However, all packets sent are lost, indicating that our development environment cannot access the internet.

![IMAGE](/images/3-developmentEnvironment/3.1-createCloud9/007-createCloud9.png)

{{%notice note%}}
As mentioned earlier, we won't be able to install necessary dependencies for our project because of this. Therefore, in the next step, we need to enable internet access for our development environment by creating a NAT gateway.

{{%/notice%}}