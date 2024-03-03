---
title : "Preparing VPC and EC2"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 3.7 </b> "
---

Next, we will push the code to the repository on CodeCommit that we created in [step 2.5](/2-prerequiste/2.5-createCodeCommit/)

- Access CodeCommit and copy the repository's HTTPS URL.

![IMAGE](/images/3-developmentEnvironment/3.7-pushCode/001-pushCode.png)

Then, push the code to CodeCommit using the following commands:
```shell
git remote add origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/workshop-01-react
git add .
git commit -m "fist push"
git push --set-upstream origin master
```
![IMAGE](/images/3-developmentEnvironment/3.7-pushCode/002-pushCode.png)

Accessing CodeCommit, we can see that the source code has been successfully pushed.

![IMAGE](/images/3-developmentEnvironment/3.7-pushCode/003-pushCode.png)