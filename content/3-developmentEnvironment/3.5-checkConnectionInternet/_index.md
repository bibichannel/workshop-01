---
title : "Check internet connection"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---

fter successfully enabling internet access for the EC2 instance in the private subnet to connect to the internet, we return to the Cloud9 IDE interface to proceed with the following:
- `curl google.com`

![IMAGE](/images/3-developmentEnvironment/3.5-checkConnectionInternet/001-checkInternet.png)

- `ping 8.8.8.8`

![IMAGE](/images/3-developmentEnvironment/3.5-checkConnectionInternet/002-checkInternet.png)

As observed, the EC2 instance has successfully connected to the internet.