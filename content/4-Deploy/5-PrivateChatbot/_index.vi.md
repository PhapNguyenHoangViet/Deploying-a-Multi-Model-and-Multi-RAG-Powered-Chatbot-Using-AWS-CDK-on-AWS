+++
title = "Chatbot riêng tư"
date = "`r Sys.Date()`"
weight = 5
chapter = false
pre = "<b>4.5. </b>"
+++

#### Chatbot riêng tư
Cho phép triển khai một chatbot riêng tư thông qua thiết lập CLI `npm run config`.

- Trang web chỉ có thể truy cập trong VPC với một Application Load Balancer ở phía trước trang web lưu trữ trên S3.
- APIs và Web Sockets Appsync riêng tư.
- VPC endpoints cho các dịch vụ AWS.
- Sử dụng chứng chỉ AWS Private CA.
- Sử dụng Amazon Route 53 Private Hosted Zone và Tên miền.

**Điều kiện tiên quyết: Triển khai Chatbot Riêng Tư**
1. [Chứng chỉ ACM được cấp bởi AWS Private CA](https://docs.aws.amazon.com/acm/latest/userguide/gs-acm-request-private.html) cho tên miền bạn chọn (ví dụ: chatbot.example.org).
2. Một Route 53 **Private Hosted Zone** (ví dụ: cho example.org).

**Trong quá trình chạy `npm run config`:**

```
$ ✔ Do you want to deploy a private website? I.e only accessible in VPC (Y/n) · 
true
$ ✔ ACM certificate ARN · 
arn:aws:acm:us-east-1:1234567890:certificate/12345678-1234-1234-1234-12345678
$ ✔ Domain for private website · 
chatbot.example.org
```


**Sau khi triển khai riêng tư:**
- Trong Route 53, [liên kết VPC đã tạo với Private Hosted Zone (PHZ)](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zone-private-associate-vpcs.html).
- Trong PHZ, [thêm một "A Record"](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-to-elb-load-balancer.html) với subdomain bạn chọn (ví dụ: chatbot.example.org) trỏ đến Alias của Application Load Balancer cho trang web.
