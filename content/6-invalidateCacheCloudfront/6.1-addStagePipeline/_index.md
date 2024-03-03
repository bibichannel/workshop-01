---
title : "Add Stage in CodePipeline"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 6.1 </b> "
---

- Access the **CodePipeline** console, select **Pipeline**, click on **react-deploy-pipeline**, then choose **Edit**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/001-add.png)

- Scroll down to the bottom and click **Add stage**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/002-add.png)

- Enter the name for the stage as `InvalidateCloudfront`. Then click **Add stage**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/003-add.png)

- Select **Add action group**,

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/004-add.png)

- Next, name it as `Invalidation`.
- Choose the **Action provider** as **CodeBuild**. We will use CodeBuild to execute a command to call the CloudFront API for invalidation.
- For the region, select the same as the region of CodePipeline.
- Select Input artifact as **SourceArtif**.
- Click **Create project**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/005-add.png)

- The interface for **Create build project** appears. Name the project `workshop-01-invalidation`.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/006-add.png)

- For the service role, select **New service**. With this service, your first build will fail because it doesn't have access to CloudFront to create invalidations. So attach the **CloudFrontFullAccess** policy to it.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/007-add.png)

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/008-add.png)

- Next, in the buildspec section, add the configuration directly as follows:

```yaml
version: 0.2

phases:
  build:
    commands:
        # Invalidate
        - aws cloudfront create-invalidation --distribution-id E350YLUNXCX5JQ --paths "/*"
     
```

Where  `E350YLUNXCX5JQ`  is the distribution id of CloudFront we created in [step 5.3](../../5-publicWebsite&Distribution/5.3-createCloudfront/)

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/009-add.png)

- Keep the remaining configurations as default.
- Then press **Continue to Codepipeline**.
- Back in the **Edit action** interface, we see the notification that our project has been successfully created.
- Choose single build and click **Create Action**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/010-add.png)

- The action has been created, scroll up and click **Save**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/011-add.png)


