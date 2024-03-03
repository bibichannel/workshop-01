---
title : "Public website & distribution"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

In this section, we will continue using CloudFront and Route 53 to publish our website to the internet.

We could also publish the website directly on S3 without using these two services, but:

| Amazon S3 | CloudFront|
| ----------- | ----------- |
| Deploying the website directly on Amazon S3 is a simple and cost-effective way to host static websites. | CloudFront provides a caching layer in front of the website, improving access performance by reducing latency and loading content from edge locations close to users. |
| However, it doesn't support features like HTTP/2, TLS termination, or caching at the origin. | CloudFront offers higher security through features such as SSL/TLS encryption, access control, and DDoS protection capabilities. |

Therefore, I see no reason why we shouldn't use CloudFront to speed up the website and enhance its security.

And Route 53 will help us manage our domain, directing the domain to the CloudFront distribution resource URL.

### Content
- [Create Hosted zone](5.1-createHostedZone/)
- [Create ACM](5.2-createACM/)
- [Create Cloudfront distribution](5.3-createCloudfront/)
- [Create record](5.4-createRecord/)

