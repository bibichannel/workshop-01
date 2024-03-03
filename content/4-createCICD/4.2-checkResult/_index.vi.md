---
title : "Kiểm tra kết quả"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

Sau khi chạy 1 pipeline từ CodePipeline mà ta vừa mới tạo. Tiếp sau đây ta sẽ kiểm tra kết quả trả về.

1. Kiểm tra bucket

- Ta truy cập vào console của [S3](https://s3.console.aws.amazon.com/s3/buckets)
- Ở đây ta thấy ngoài bucket mà ta đã tạo ở [bước 2.4](../../2-prerequiste/2.4-createS3/)
- Thì CodePipeline sẽ tạo ra thêm 1 bucket nữa để nó lưu trữ artifact trong quá trình pipeline

![IMAGE](/images/4-createCICD/4.2-checkResult/001-check.png)

- Truy cập **workshop-01-react** bucket. Ta thấy tất cả các file ta cần trong tệp **build** của dự án đã có trong bucket này. 

{{%notice tip%}}
Tới bước này bạn hoàn toàn có thể public nội dung này lên internet từ S3 và người dùng có thể truy cập website của bạn. Nhưng sẽ tôt hơn nếu bạn sử dụng thêm dịch vụ CDN và route53 để tăng tốc website của bạn, sử dụng tên miền của chính bạn và tăng cường bảo mật.

{{%/notice%}}

![IMAGE](/images/4-createCICD/4.2-checkResult/002-check.png)

- Truy cập bucket còn lại ta thấy 2 folder được tạo là **BuildArtif** và **SourceArtif** trong này sẽ chứa các artifact(.Zip) của source stage và build stage trong pipepline.

![IMAGE](/images/4-createCICD/4.2-checkResult/003-check.png)
![IMAGE](/images/4-createCICD/4.2-checkResult/004-check.png)
![IMAGE](/images/4-createCICD/4.2-checkResult/005-check.png)


2. Kiểm tra CodeBuild
- Truy cập vào **Build project** ta thấy. Có 1 build đã thành công với **build number** là **1**, **Submitter** là **codepipeline**

![IMAGE](/images/4-createCICD/4.2-checkResult/006-check.png)

- Phase của code build đều success
- Để hiểu hơn về các phase trong một code build, bạn có thể tham khảo thêm [tại đây](https://docs.aws.amazon.com/codebuild/latest/APIReference/API_BuildPhase.html).

![IMAGE](/images/4-createCICD/4.2-checkResult/007-check.png)

3. Kiểm tra CloudWatch
- Truy cập vào console của **CloudWatch**, click vào **Log groups** ta thấy log group của dịch vụ CodeBuild.

![IMAGE](/images/4-createCICD/4.2-checkResult/008-check.png)

- Mỗi log group sẽ chứa tập hợp các **log streams**, mỗi log streams nó chính là lưu thông tin của một quá trình build của project. 

![IMAGE](/images/4-createCICD/4.2-checkResult/009-check.png)

- Nhấn vào log stream để xem chi tiết.

![IMAGE](/images/4-createCICD/4.2-checkResult/010-check.png)

- Đây chính là thông tin của một quá trình build từ download source cho đến lúc push artifact.