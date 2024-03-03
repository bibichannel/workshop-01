---
title : "Create S3 bucket"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

In the initial diagram, we also have an S3 Bucket as the storage location for the static website, so let's proceed to create it as it's relatively straightforward.

1. In the Create bucket interface:
- **AWS region**: Choose the S3 bucket in the region where we are conducting the lab. Currently, I am doing the lab in the **N. Virginia (us-east-1)** region.
- **Bucket Type:** Within the scope of this lab, we'll choose **General purpose**.
- Enter a Bucket name. It must be unique. You can choose any name; here, I'll create a bucket named `workshop-01-react`.

{{%notice info%}}
AWS S3 can be publicly accessible, and it provides us with access to its bucket and objects via REST API. Essentially, the path must adhere to DNS and cannot have duplicate domain names. Therefore, bucket names need to be unique to access groups and objects via the REST API endpoint.

{{%/notice%}}

![S3](/images/2-prerequiste/2.4-createS3/001-createS3.png)

Below, we will keep the default configuration and click on **Create bucket**.

![S3](/images/2-prerequiste/2.4-createS3/002-createS3.png)

{{%notice note%}}
Pay attention to the **Block all public access** section. We will still enable this feature because the content distribution to the public internet will be done through CloudFront, not the S3 bucket.

{{%/notice%}}
