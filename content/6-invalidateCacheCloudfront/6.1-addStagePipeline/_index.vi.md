---
title : "Thêm stage vào CodePipeline "
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 6.1 </b> "
---

- Truy cập vào console của **CodePipeline**, chọn **Pipeline**, click vào **react-deploy-pipline**, sau đó chọn **Edit**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/001-add.png)

- Sau đó cuộn xuống dưới cùng click **Add stage**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/002-add.png)

- Nhập tên cho stage `InvalidateCloudfront`. Sau đó click **Add stage**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/003-add.png)

- Chọn **Add action group**,

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/004-add.png)

- Tiếp theo ta đặt tên là `Invalidation`.
- **Action provider** ta chọn là CodeBuild. Ta sẽ sử dụng CodeBuild để chạy một câu lệnh gọi api của cloudfront yêu cầu nó invalidation.
- Phần region ta chọn trùng với region của CodePipeline.
- Input artifact ta sẽ chọn **SourceArtif**
- Nhấn **Create project**

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/005-add.png)

- Giao diện **Create build project** hiện ra. Ta đặt tên cho project là `workshop-01-invalidation`.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/006-add.png)

- Service role ta sẽ chọn **New service**. Với service này bạn sẽ build thất bại lần đầu tiên, vì nó không có quyền truy cập Cloudfront để tạo Invalidate. Vì vậy bạn hãy đính kèm thêm policy `CloudFrontFullAccess`.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/007-add.png)

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/008-add.png)

- Tiếp theo tới phần buildspec, ta sẽ thêm cấu hình trực tiếp như sau:

```yaml
version: 0.2

phases:
  build:
    commands:
        # Invalidate
        - aws cloudfront create-invalidation --distribution-id E350YLUNXCX5JQ --paths "/*"
     
```

Với `E350YLUNXCX5JQ` là distribution id của Could ta tạo ở [bước 5.3](../../5-publicWebsite&Distribution/5.3-createCloudfront/)

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/009-add.png)

- Các phần cấu hình còn lại ta giữ như mặc định.
- Sau đó ta nhấn **Continue to Codepipeline**
- Quay trở lại giao diện **Edit action**, ta thấy thông báo project của chúng ta đã tạo thành công.
- Chọn single build và nhấn **Create Action**

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/010-add.png)

- Action đã được tạo, ta cuộn chuột lên trên và click **Save**.

![IMAGE](/images/6-invalidateCacheCloudfront/6.1-addStagePipeline/011-add.png)
