---
title : "Triển khai CI/CD Pipeline"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

Để triển khai CI/CD Pipeline, AWS cung cấp cho ta bộ công cụ CodePipeline để thực hiện tự động hoá giữa quá phát triển và triển khai ứng dụng của chúng ta.

CodePipeline là dịch vụ AWS cho phép chúng ta xây dựng qui trình khiển khai ứng dụng một cách liên tục và tự động. Với cách thức cấu hình đơn giản, CodePipeline có khả năng mô hình hoá trực quan các bước cần thiết để biên dịch, kiểm thử và triển khai các phiên bản cập nhật cho một ứng dụng hoặc dịch vụ.

Tiếp sau đây sẽ là hướng dẫn chúng ta xây dựng một CI/CD Pipeline cho ứng dụng React của chúng ta.

### Nội dung
- [Tạo CodePipeline](4.1-createCodePipeline/)
- [Kiểm tra thành quả](4.2-checkResult/)
