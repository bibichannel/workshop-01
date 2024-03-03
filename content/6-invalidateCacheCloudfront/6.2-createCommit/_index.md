---
title : "Create Commit"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 6.2 </b> "
---

Ta sẽ thực hiện chỉnh sửa code của dự án, commit lên CodeCommit để pipeline của chúng ta chạy tự động sau đó nó sẽ deploy lên S3 bucket và tự động thực hiện Invalidation Cloudfront để cập nhật nội dung code mới nhất.

1. Chỉnh sửa source code.
- Để cho nhanh mình sẽ edit thẳng trên console của CodeCommit. Thực tế sẽ không như vậy, hãy sử dụng Cloud9 để phát triển dự án của chúng ta
- Chỉnh như hình dưới đây và commit nó.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/001-commit.png)

2. Quay lại CodeCommit ta thấy nó đã nhận thấy thay đổi trên source code của chúng ta và pipeline của chúng ta đã được kích hoạt. Sau khi đợi một khoảng thời gian pipeline của chúng ta đã chạy thành công.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/002-commit.png)

- Chọn view detail ở action **InvalidateCloudfront** ta thấy thông tin lệnh call API của ta đã thành công và Invalidation đã được tạo.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/003-commit.png)

- Mở console của **Cloudfront** ta truy cập vào **Distributions** và chọn **Invalidations** ta thấy thông tin của Invalidation được tạo ra.

![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/004-commit.png)

- Tiếp theo ta truy cập `https://workshop-01.bibichannel.site` để kiểm tra sự thay đổi.

| Before | After|
|:------:|:------:|
|![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/006-commit.png)|![IMAGE](/images/6-invalidateCacheCloudfront/6.2-createCommit/005-commit.png)|

