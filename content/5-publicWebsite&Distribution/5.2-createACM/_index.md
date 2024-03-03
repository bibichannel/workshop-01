---
title : "Create ACM"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

Utilizing the **AWS Certificate Manager (ACM)** facilitates the provisioning, management, and deployment of public and private SSL/TLS certificates for use with AWS services and resources. ACM streamlines the process of purchasing, uploading, and renewing SSL/TLS certificates, saving significant time.

- Access the ACM console, select **Request certificate**, and click **Next**.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/001-createACM.png)

- Request a certificate for the child domain `workshop-01.bibichannel.site` by entering it in the **Fully qualified domain name field**.
- For **Validation method**, it's advisable to use **DNS validation** for a quicker validation process.
- Leave the rest as default.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/002-createACM.png)

- Click **Create**, and the ACM is created, but its status will be **Pending validation**. The next step is to create a record for the validation process to succeed.
- As AWS services are tightly integrated, you simply need to click **Create record in Route 53**.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/003-createACM.png)

- The record creation interface appears, generating a CNAME record for validation of our domain.
- Click **Create records**.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/004-createACM.png)

- Record creation is successful.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/005-createACM.png)

- After creating the record, ACM successfully validates our domain, and now our domain has an SSL/TLS certificate. You can access `https://workshop-01.bibichannel.site` to view the certificate.

![IMAGE](/images/5-publicWebsite&Distribution/5.2-createACM/006-createACM.png)
