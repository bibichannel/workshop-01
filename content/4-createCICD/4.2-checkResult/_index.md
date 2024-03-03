---
title : "Check the result"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

After running a pipeline from CodePipeline that we've just created, let's proceed to check the returned results.

1. Bucket Inspection:
- To begin, we access the  [S3](https://s3.console.aws.amazon.com/s3/buckets)
- Here, apart from the bucket created in [step 2.4](../../2-prerequiste/2.4-createS3/)

- CodePipeline generates an additional bucket to store artifacts during the pipeline process.

![IMAGE](/images/4-createCICD/4.2-checkResult/001-check.png)

- Navigate to the **workshop-01-react** bucket. We observe all necessary files within the build directory of our project present in this bucket. 

{{%notice tip%}}
At this stage, you can completely make this content public on the internet from S3, and users can access your website. However, it's advisable to utilize additional CDN and Route 53 services to enhance your website's speed, use your own domain, and bolster security.

{{%/notice%}}

![IMAGE](/images/4-createCICD/4.2-checkResult/002-check.png)

- Accessing the other bucket, we find two folders created: **BuildArtif** and **SourceArtif**, where artifacts (.Zip) from the source stage and build stage in the pipeline are stored.

![IMAGE](/images/4-createCICD/4.2-checkResult/003-check.png)
![IMAGE](/images/4-createCICD/4.2-checkResult/004-check.png)
![IMAGE](/images/4-createCICD/4.2-checkResult/005-check.png)


2. CodeBuild Examination:
- Accessing the **Build project**, we observe:
-One successful build with **build number** as **1**, **Submitter** as **codepipeline**.

![IMAGE](/images/4-createCICD/4.2-checkResult/006-check.png)

- All phases of the code build are successful.
- For a deeper understanding of the phases in a code build, you can refer [here](https://docs.aws.amazon.com/codebuild/latest/APIReference/API_BuildPhase.html).

![IMAGE](/images/4-createCICD/4.2-checkResult/007-check.png)

3. CloudWatch Verification:
Accessing the **CloudWatch** console, clicking on **Log groups**, we find the log group for the CodeBuild service.

![IMAGE](/images/4-createCICD/4.2-checkResult/008-check.png)

Each log group contains sets of **log streams**, where each log stream represents information about a build process of a project. 

![IMAGE](/images/4-createCICD/4.2-checkResult/009-check.png)

Clicking on a log stream provides detailed information.

![IMAGE](/images/4-createCICD/4.2-checkResult/010-check.png)

This represents the information of a build process from downloading source to pushing artifacts.
