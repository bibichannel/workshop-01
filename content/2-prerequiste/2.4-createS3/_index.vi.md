---
title : "Tạo S3 bucket"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 2.4 </b> "
---

Trong diagram ban đầu chúng ta có thêm S3 Bucket là nơi lưu trữ static website nên ta sẽ tiến hành tạo luôn vì nó khá dễ dàng.

1. Trong giao diện Create bucket
- **AWS reigon** ta chọn S3 bucket tại region mà ta đang làm lab. Hiện tại mình đang làm lab tại **N.Virginia (us-east-1)** region.
- **Bucket Type** trong khuôn khổ bài lab ta chọn **General purpose** là đủ.
- Nhập Bucket name, phải nhập tên duy nhất, bạn có thể chọn tùy ý ở đây mình tạo bucket với tên là `workshop-01-react`

{{%notice info%}}
AWS S3 có thể truy cập public và AWS S3 cung cấp cho chúng ta cách access vào bucket và object của nó bằng API REST.
Về cơ bản, đường dẫn cần phải tuân thủ DNS và không thể có hai tên miền giống nhau. Vì vậy, bucket names cần phải là duy nhất để truy xuất nhóm và đối tượng bằng điểm cuối REST API.

{{%/notice%}}

![S3](/images/2-prerequiste/2.4-createS3/001-createS3.png)

Ở dưới ta sẽ giữ nguyên cấu hình mặc định và click **Create bucket**.

![S3](/images/2-prerequiste/2.4-createS3/002-createS3.png)

{{%notice info%}}
Chú ý một chút ở phần Block all public access. Ta sẽ vẫn bật tính năng này vì thứ phân phối nội dung chúng ta ra public internet sẽ là CloudFront chứ không phải S3 bucket.

{{%/notice%}}
