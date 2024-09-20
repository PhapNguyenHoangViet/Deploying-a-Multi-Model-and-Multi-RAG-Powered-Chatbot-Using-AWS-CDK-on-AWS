+++
title = "Tên miền công khai tùy chỉnh"
date = "`r Sys.Date()`"
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++

#### Tên miền công khai tùy chỉnh
Cho phép chỉ định một tên miền tùy chỉnh thông qua thiết lập CLI `npm run config`.
- Sử dụng Chứng chỉ Công cộng của AWS
- Sử dụng Amazon Route 53 Public Hosted Zone và Tên miền

**Điều kiện tiên quyết:**
1. Chứng chỉ AWS đã được cấp và xác thực (https://docs.aws.amazon.com/acm/latest/userguide/dns-validation.html) ở vùng us-east-1 cho tên miền bạn chọn (ví dụ: chatbot.example.org).
2. Một Route 53 Public Hosted Zone (ví dụ: cho example.org).

**Trong quá trình npm run config**

```
$ ✔ Do you want to deploy a private website? I.e only accessible in VPC (y/N) · 
false
$ ✔ Do you want to provide a custom domain name and corresponding certificate arn for the public website ? (y/N) ·
true
$ ✔ ACM certificate ARN with custom domain for public website. Note that the certificate must resides in us-east-1 · 
arn:aws:acm:us-east-1:1234567890:certificate/12345678-1234-1234-1234-12345678
$ ✔ Custom Domain for public website · 
chatbot.example.org

```


**Sau khi triển khai:**

Trong Route 53 Hosted Zone của bạn, thêm một "A Record" trỏ đến CloudFront Alias (https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-to-cloudfront-distribution.html).

