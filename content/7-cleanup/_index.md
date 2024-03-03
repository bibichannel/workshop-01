---
title : "Resource Cleanup"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

Let us proceed to dismantle the resources in accordance with the following list:

1. Terminate Cloud9.
2. Remove the Nat gateway.
3. Release the Elastic IP.
4. Delete the Interface endpoint.
5. Eliminate the VPC.
6. Erase the A record and CNAME record of the Hosted zoned Route 53.
7. Remove the Hosted zoned Route 53.
8. Invalidate CloudFront and then proceed with deletion.
9. Eliminate the NS record from your domain registrar.
10. Delete the Certificates from ACM.
11. Remove CodePipeline.
12. Delete CodeCommit.
13. Eliminate CodeBuild.
14. Empty the objects within the bucket and proceed to delete the S3 bucket.
15. Remove the role and associated policies.