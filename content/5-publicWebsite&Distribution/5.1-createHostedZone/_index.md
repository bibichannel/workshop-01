---
title : "Create hosted zone"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

Here, as I own a domain named `bibichannel.site` with another domain registrar, I will create a hosted zone in Route 53 to manage my subdomain.

This subdomain will be used to resolve to the URL resource of the CloudFront distribution.

- Access the Route 53 Console, select **Hosted zones**, then click **Create hosted zone**.

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/001-hostedZone.png)

- In the **Domain name** field, enter `workshop-01.bibichannel.site` to create a child domain for **bibichannel.site**.
- In the **Description**, enter `The hosted zone used for workshop-01.bibichannel.site domain`.
- Choose **Public hosted zone** for the **Type**.

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/002-hostedZone.png)

- After creation, you will see 2 records: **NS** and **SOA**.
- The **NS (Name Server)** record contains information about AWS name servers routing requests related to this domain.
- The **SOA (Start of Authority)** record in AWS Route 53 is an essential DNS resource record containing management information about a specific domain. The SOA record is typically used to identify the primary name server for the domain, as well as other management information such as Zone ID, administrator's email address, etc.
- Learn more [here](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/SOA-NSrecords.html).

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/003-hostedZone.png)

- Next, we need to create NS records at the domain registrar where we registered the domain to point to AWS's **Name Servers**.

![IMAGE](/images/5-publicWebsite&Distribution/5.1-createHostedZone/004-hostedZone.png)

- These **NS** records will determine which server will manage the information for our child domain. And here, it's AWS **Route 53**.

