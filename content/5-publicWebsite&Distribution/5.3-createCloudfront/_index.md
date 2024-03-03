---
title : "Create Cloudfront"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

In this step, we'll create a CloudFront distribution to distribute the content of our website.

- Access the **CloudFront** console, and for the **Origin domain**, select the URL of the **workshop-01-react** S3 bucket.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/001-createCloudfront.png)

- For Origin access identity, select Legacy access identities. You can choose from the list or select **Create new OAI**.
- Tick **Yes, update the bucket policy** under **Bucket policy**.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/002-createCloudfront.png)

- For **Compress objects automatically**, select **Yes** to compress content when sending it to viewers.
- **Viewer protocol policy** will be **Redirect HTTP to HTTPS**.
- Keep the rest as default.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/003-createCloudfront.png)

- Scroll down to **WAF**, for this lab, we won't use it. Select **Do not enable security protections**.
- We'll limit our content distribution to a few regions instead of global. So for **Price class**, select **Use North America, Europe, Asia, Middle East, and Africa**.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/004-createCloudfront.png)

- In **Alternate domain name (CNAME)**, enter your child domain: `workshop-01.bibichannel.site`.
- For **Custom SSL certificate**, choose the ACM certificate we created in [step 5.2](../5.2-createACM/).

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/005-createCloudfront.png)

- In **Default root object**, enter `index.html`.
- Then press **Create distribution**.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/006-createCloudfront.png)

- Our CloudFront is successfully created with the URL: `https://d1y4dlqj807yu9.cloudfront.net`. The distribution process will take place within a short time, typically a few minutes.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/007-createCloudfront.png)

- Upon accessing, we see that the website is working.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/008-createCloudfront.png)

- However, when accessing `https://workshop-01.bibichannel.site`, our website is not available.

![IMAGE](/images/5-publicWebsite&Distribution/5.3-createCloudfront/009-createCloudfront.png)

- This is because we missed creating an A record DNS for the child domain pointing to the CloudFront resources URL. The next step is to create the record.