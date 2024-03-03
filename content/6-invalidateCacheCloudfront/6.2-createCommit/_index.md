---
title : "Create Commit"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 6.2 </b> "
---

We will edit the project's code, commit to CodeCommit so that our pipeline runs automatically, then it will deploy to the S3 bucket and automatically perform Invalidation Cloudfront to update the latest code content.

1. To speed things up, I'll edit the source code directly in the CodeCommit console. In reality, you should use a proper development environment like Cloud9 for your project development.

- Edit the code as shown in the image below and commit it.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/001-commit.png)

2. Back in CodeCommit, you'll see that it has detected the changes in our source code, and our pipeline has been triggered. After waiting for a while, our pipeline has run successfully.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/002-commit.png)

- Select view detail on the **InvalidateCloudfront** action to see that our API call command has been successful and the Invalidation has been created.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/003-commit.png)

- Go to the **CloudFront** console, access **Distributions**, and select **Invalidations**. You'll see the information for the created Invalidation.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/004-commit.png)

- Next, access `https://workshop-01.bibichannel.site` to check for the changes.

| Before | After|
|:------:|:------:|
|![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/006-commit.png)|![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/005-commit.png)|

