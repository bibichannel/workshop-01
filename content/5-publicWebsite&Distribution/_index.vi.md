---
title : "Public website"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

Ở phần hướng dẫn này chúng ta sẽ tiếp tục sử dụng Cloudfront và Route53 để public website của chúng ta ra ngoài internet. 

Chúng ta cũng có thể public website trên S3 luôn mà không cần sử dụng 2 dịch vụ trên nhưng:

| Amazon S3 | CloudFront|
| ----------- | ----------- |
| Việc đưa trang web trực tiếp lên Amazon S3 là một cách đơn giản và chi phí thấp để triển khai trang web tĩnh. | CloudFront cung cấp một lớp cache phía trước cho trang web, giúp cải thiện hiệu suất truy cập bằng cách giảm độ trễ và tải nội dung từ các edge location gần người dùng. |
| Tuy nhiên, nó không hỗ trợ các tính năng như HTTP/2, TLS termination, hoặc cache phía trước. | CloudFront cung cấp khả năng bảo mật cao hơn thông qua tính năng như SSL/TLS encryption, access control, và khả năng chống DDoS. |

Vì vậy mình nghĩ rằng chả có lí do gì mà ta không sử dụng Cloudfront để tăng tốc website, cũng như bảo mật nó tốt hơn.

Và Route 53 sẽ giúp ta quản lí tên miền của mình, trỏ domain tới url Cloudfront distribution resource.

### Nội dung
- [Tạo Hosted zone](5.1-createHostedZone/)
- [Tạo ACM](5.2-createACM/)
- [Tạo Cloudfront distribution](5.3-createCloudfront/)
- [Tạo record](5.4-createRecord/)