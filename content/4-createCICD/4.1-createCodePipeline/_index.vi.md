---
title : "Tạo CodePipeline"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

1. Truy cập vào AWS CodePipeline
- Chọn Pipeline
- Chọn Create pipeline

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/001-createPipeline.png)

2. Trong giao diện tạo CodePipeline
- Nhập `react-deploy-pipeline` vào **Pipeline name**
- **Pipeline type** trong bài lab này ta chọn **V1** là đủ 
- Với **Excution mode** ta chọn **Superseded**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/002-createPipeline.png)

{{%notice info%}}
**Superseded (Bị thay thế)** được hiểu là khi một thực thi mới được kích hoạt (chẳng hạn khi bạn đưa ra một thay đổi vào mã nguồn), nó sẽ được bắt đầu và thực hiện các bước trong quy trình triển khai. Trong quá trình này, nếu có một thực thi khác đang chạy cùng lúc, quy trình triển khai có thể tự động dừng và thay thế thực thi cũ hơn bằng thực thi mới hơn.

{{%/notice%}}

- Đối với **Service role** chọn **New service role**
- Và tích chọn **Allow AWS CodePipeline to create a service role so it can be used with this new pipeline**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/003-createPipeline.png)

- Ở Advance Setting ta chọn **Artifact store** là **Default location** để lưu trữ artifact trong cùng một region với CodePipeline
- Về việc mã hoá oject khi lưu trữ trên S3 ta chọn sử dụng **Default AWS Managed Key** làm **Encryption key**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/004-createPipeline.png)

- Chọn **Next**

3. Đối với Add source stage
- **Source provider**, chọn **AWS CodeCommit**
- **Repository name**, chọn **workshop-01-react**
- Đối với **Branch name**, chọn **master**
- Tích chọn sử dụng **Amazon CloudWatch Events** để tự động bắt đầu pipeline có thay đổi trên repo.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/005-createPipeline.png)

- Phần **Output artifact format** ta chọn **CodePipeline default**. Artifact của ta sẽ là source code được clone về đóng zip lại nhưng sẽ không chứa các metadata của git.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/006-createPipeline.png)

- Chọn **Next**

4. Phần **Build provider** chọn **AWS CodeBuild**
- Phần **Region** sẽ trùng region với dự án của chúng ta **N.Virginia**
- Phần **Project Name** vì ta chưa tạo **Codebuild project** nên ta chọn **Create project**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/007-createPipeline.png)

Một tab mới hiện ra cho chúng ta cấu hình CodeBuild project
- Ta nhập `workshop-01-react` vào mục **Project Name**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/008-createPipeline.png)

- Về phần cấu hình môi trường(EC2) để CodeBuild thực hiện build project của chúng ta hãy chọn như hình dưới đây:

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/009-createPipeline.png)

- Tiếp tục chọn **New service role**

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/010-createPipeline.png)

- Ở phần **BuildSpec**, trong khuôn khổ của bài lab này ta sẽ thực hiện thêm cấu hình trực tiếp vào phần **Build Commands**. 

{{%notice info%}}
Còn thực tế họ sẽ thêm một file `buildspec.yml` vào root repo của dự án. Điều này giúp cho developer có thể dễ dàng chỉnh sửa quá trình build mà không cần phải truy cập vào console CodeBuild của aws.
Mà chưa chắc họ đã có quyền truy cập được.

{{%/notice%}}

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/011-createPipeline.png)

Cầu hình được thêm vào như sau:
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

Nhìn sơ qua thì cấu hình trên miêu tả quá trình ta build source code của chúng ta trên môi trường được cài nodejs version 18, thực hiện các lệnh shell và đẩy ra artifact là những gì có trong thư mục **build**.

Về syntax và ví dụ về cấu hình buildspec bạn có thể tham khảo thêm [tại đây](https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html).

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/012-createPipeline.png)

- Về log ta chọn Cloudwatch log để xem log quá trình build của CodeBuild.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/013-createPipeline.png)

- Chọn **Continue to CodePipeline**
- Sau khi quay lại giao diện tạo profile của CodePipeline ta thấy phần project name đã được tự động thêm vào Codebuild project mà ta vừa mới tạo và thông báo tạo Codebuild project thành công.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/014-createPipeline.png)

- Về **Build type** ta chọn **Trigger single build** điều này có nghĩa là mỗi lần bạn kích hoạt một build, CodeBuild sẽ tạo ra một container build riêng biệt để xây dựng mã nguồn của bạn. 

- Không như batch build, CodeBuild sẽ tập hợp nhiều phiên bản của mã nguồn và xây dựng chúng trong cùng một container build. Và trong bài lab này ta đương nhiên là không cần dùng batch build để làm gì cả.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/015-createPipeline.png)

5. Đối với **Deploy stage**
- Ta chọn deploy lên **S3**
- **Region** của S3 là ở **N.Virginia**
- Bucket ta chọn **workshop-01-react** ta tạo ở [bước 2.4](../../2-prerequiste/2.4-createS3/)
- Tích chọn **Extract file before deploy** để giải nén các tệp ra bucket của chúng ta.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/016-createPipeline.png)

- Chọn **Next**
- Bước tiếp theo sẽ là review lại quá trình mình tạo profile cho CodePipeline

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/017-createPipeline.png)

6. Tạo thành công CodePipeline
Sau khi tạo CodePipeline nó sẽ thực hiện chạy piple lần đầu tiên 

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/018-createPipeline.png)

Sau khi đợi một lúc thì ta thấy pipeline đã chạy success.

![IMAGE](/images/4-createCICD/4.1-createCodePipeline/019-createPipeline.png)
