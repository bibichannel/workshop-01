---
title : "Development Environment"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---


In this step, we will utilize the Cloud9 service to deploy our React App.

**AWS Cloud9** is an integrated development environment (IDE) that allows you to write, run, and debug your code in the browser. It includes a code editor, debugger, and command-line interface. Cloud9 comes pre-packaged with necessary tools for popular programming languages such as JavaScript, Python, PHP, etc.

Additionally, it allows us to create a Cloud9 no-ingress EC2 instance to enhance security during the web application development process. It involves creating an EC2 instance in a private subnet and using Session Manager to connect from Cloud9 to our EC2 instance, as illustrated in the diagram below:

![IMAGE](/images/3-developmentEnvironment/001-developmentEnvironment.png)

Creating an EC2 instance for the Cloud9 service in a private subnet and setting up interface endpoints for SSM is a standard procedure.

**So why do we need to add a public subnet and a NAT Gateway?**

This is because when deploying a development environment, you still need to access the internet to download dependencies for your project. Without being linked to a NAT Gateway placed in a public subnet, the private subnet cannot access the internet.

You can refer to more details [here](https://docs.aws.amazon.com/cloud9/latest/user-guide/vpc-settings.html#vpc-settings-create-subnet).

According to the above model, we will go through the following steps in this section to develop our application and manage its source code:

### Content
 - [Create Cloud9](3.1-createCloud9/)
 - [Create ElasticIP](3.2-createElasticIP/)
 - [Create NAT gateway](3.3-createNatGateway/)
 - [Create Routes cho Route Table](3.4-createRoutes/)
 - [Check internet connection](3.5-checkConnectionInternet/)
 - [Create React App](3.6-createReactApp/)
 - [Push code to CodeCommit](3.7-pushCode/)
