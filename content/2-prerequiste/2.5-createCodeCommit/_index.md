---
title : "Create CodeCommit"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

We need a secure place to store our source code every time we develop an application, and along with that, we need to secure our source code.

While GitHub, Bitbucket, GitLab, etc., provide private repository storage options, they often require payment and contractual obligations, and there's no guarantee of server uptime

In contrast, AWS provides us with a service called CodeCommit, which offers private repository storage. It integrates well with other AWS services and provides security and access control through IAM.

All of these reasons convince us to use CodeCommit. In this section, we will create a repository using CodeCommit.

1. Firstly, let's create a CodeCommit repository.
- Access **CodeCommit**.
- Enter the name of the project we want to store: `workshop-01-react`.
- PEnter the description:  `Repository for react application`.
- Click **Create**.

![IMAGE](/images/2-prerequiste/2.5-createCodeCommit/001-createCodeCommit.png)

Creating a repository on CodeCommit is quite simple and fast. In just a few steps, we have a **private repository** for our project.

![IMAGE](/images/2-prerequiste/2.5-createCodeCommit/002-createCodeCommit.png)

