---
title : "Create Record"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---

- Access **Route 53**, go to **Hosted zones**, select **workshop-01.bibichannel.site**, then press **Create record**.
- Choose **Record type** as **A** and **enable Alias**.

![IMAGE](/images/5-publicWebsite&Distribution/5.4-createRecord/001-createRecord.png)

- Select **Route traffic to CloudFront**.
- Then choose the URL of the CloudFront distribution we created in [step 5.3](../5.3-createCloudfront/).
- Click **Create records**.

![IMAGE](/images/5-publicWebsite&Distribution/5.4-createRecord/002-createRecord.png)

- Go back to the URL  `https://workshop-01.bibichannel.site`
- You'll see that our website is now up. This process may take some time, so please be patient.

![IMAGE](/images/5-publicWebsite&Distribution/5.4-createRecord/003-createRecord.png)