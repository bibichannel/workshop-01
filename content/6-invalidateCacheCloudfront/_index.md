---
title : "Invadlidate cache Cloudfront"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

Upon activating a new pipeline for deployment to the S3 bucket, CloudFront remains unaware of the changes within S3, thus failing to automatically update its cache. 

Consequently, it becomes imperative to disable the cache of CloudFront to facilitate the refreshing of its content. CloudFront offers us the feature of Invalidations, which can be initiated manually or via CLI to invalidate the cache.

![IMAGE](/images/6-invalidateCacheCloudfront/001-invalidation.png)

**Shall we resort to manual intervention for this task?**

Such an approach seems antiquated, especially within the context of CI/CD. Therefore, in this section, I will elucidate the process for automating this task.

### Content
- [Add Stage in Codepipeline](6.1-addStagePipeline/)
- [Creating a Code Commit for Result Verification](6.2-createCommit/)