---
title : "Invadlidate cache Cloudfront"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

Vì khi ta kích hoạt pipeline mới deploy lên s3 bucket. Thì Cloudfront sẽ không biết được sự thay đổi của S3 để tự động cập nhật lại cache của cloudfront.

Vì thế ta cần phải vô hiệu hoá cache của Cloudfront để nó cập nhật lại nội dung mới. Cloudfront cung cấp cho chúng ta tính năng **Invalidations**. Ta có thể tạo bằng tay hoặc CLI để có thể vô hiệu hoá Cache.

![IMAGE](/images/6-invalidateCacheCloudfront/001-invalidation.png)

Chả lẽ ta lại phải làm thủ công việc này sao? Với quy trình CI/CD thì điều này không thể chấp nhận được. Nên trong phần này mình sẽ hướng dẫn các bạn làm nó tự động.

### Nội dung
- [Thêm stage trong Codepipeline](6.1-addStagePipeline/)
- [Tạo code commit để check kết quả](6.2-createCommit/)