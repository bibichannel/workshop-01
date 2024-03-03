---
title : "Create CodePipeline"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

1. Accessing AWS CodePipeline:
- Select **Pipeline**.
- Choose **Create pipeline**.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/001-createPipeline.png)

2. Within the CodePipeline creation interface:
- Enter `react-deploy-pipeline` into the **Pipeline name** field.
- For **Pipeline type**, in this lab, we opt for **V1**.
- Regarding **Excution mode**, we select **Superseded**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/002-createPipeline.png)

{{%notice info%}}
**Superseded** refers to the scenario where a new execution is triggered (such as when a change is introduced to the source code), it initiates and proceeds with deployment steps. During this process, if another execution is running concurrently, the deployment process may automatically halt and replace the older execution with the newer one.

{{%/notice%}}

- For  **Service role**, choose **New service role**.
- Additionally, check the box **Allow AWS CodePipeline to create a service role so it can be used with this new pipeline**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/003-createPipeline.png)

- In the Advanced Settings, designate **Artifact store** as **Default location** to store artifacts in the same region as CodePipeline.
- For encryption of objects stored on S3, opt to utilize **Default AWS Managed Key** as the **Encryption key**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/004-createPipeline.png)

- Select **Next**

3. For the Add source stage:
- Choose **AWS CodeCommit** as the **Source provider**.
- Select `workshop-01-react` as the **Repository name**.
- Choose **master** for the **Branch name**.
- Check the box to utilize **Amazon CloudWatch Events** for automatically triggering the pipeline upon changes in the repository.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/005-createPipeline.png)

- Regarding the **Output artifact format**, opt for CodePipeline default. Our artifact will be the cloned source code compressed into a zip file but excluding git metadata.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/006-createPipeline.png)

- Select **Next**

4. Under **Build provider**, choose **AWS CodeBuild**.
- Ensure the **Region** aligns with our project's, i.e., **N. Virginia**.
- As we haven't yet created a CodeBuild project, select **Create project**.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/007-createPipeline.png)

This prompts a new tab for configuring the **CodeBuild project**.
- Enter `workshop-01-react` in the **Project Name** field.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/008-createPipeline.png)

- For configuring the environment (EC2) for CodeBuild to execute the project build, select as illustrated below:

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/009-createPipeline.png)

- Proceed with selecting **New service role**.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/010-createPipeline.png)

- In the **BuildSpec** section, for the scope of this lab, we will directly add configurations to the **Build Commands**.

{{%notice info%}}
In practice, a `buildspec.yml` file would typically be added to the root repository of the project. This facilitates developers to easily modify the build process without needing access to the AWS CodeBuild console. However, it's not guaranteed they'd have such access

{{%/notice%}}

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/011-createPipeline.png)

The added configuration appears as follows:
```yml
version: 0.2

phases:
  install:
    runtime-versions:
      nodejs: 18
   
    commands:
        # install npm
        - npm install
       
  build:
    commands:
        # run build script
        - npm run build
     
artifacts:
  # include all files required to run the application
  files:
    - '**/*'
  base-directory: build
```

A quick glance shows that the configuration outlines the process of building our source code on an environment with Node.js version 18 installed, executing shell commands, and outputting artifacts from the build directory.

For syntax and further examples of BuildSpec configurations, refer to [here](https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html).

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/012-createPipeline.png)

- For logging, select CloudWatch log to view the build logs of CodeBuild.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/013-createPipeline.png)

- Choose **Continue to CodePipeline**
- Upon returning to the CodePipeline creation interface, we notice that the project name has been automatically added to the newly created CodeBuild project, and a notification of successful CodeBuild project creation.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/014-createPipeline.png)

- For Build type, select **Trigger single build**, meaning each time you initiate a build, CodeBuild generates a separate build container to compile your source code.

- Unlike batch builds, where CodeBuild aggregates multiple versions of source code and builds them in the same build container. And for this lab, batch builds aren't necessary.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/015-createPipeline.png)

5. For the **Deploy stage**
- Opt for deployment to **S3**.
- The **S3 Region** is in **N. Virginia**.
- Select the **workshop-01-react** bucket created in [step 2.4](../../2-prerequiste/2.4-createS3/)
- Check the box **Extract file before deploy** to unzip files into our bucket.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/016-createPipeline.png)

- Choose **Next**
- The subsequent step involves reviewing the process of creating the CodePipeline.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/017-createPipeline.png)

6. Successful Creation of **CodePipeline**:
- Upon creating the CodePipeline, it initiates the first pipeline run.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/018-createPipeline.png)

- After a while, the pipeline runs successfully.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/019-createPipeline.png)


