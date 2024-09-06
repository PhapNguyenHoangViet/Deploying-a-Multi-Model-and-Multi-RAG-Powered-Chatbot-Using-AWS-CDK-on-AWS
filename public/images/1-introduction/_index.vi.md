+++
title = "Giới thiệu"
date = 2020-05-14T00:38:32+07:00
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

### Tổng quan

**Kubernetes (K8s)** là một nền tảng nguồn mở, có thể mở rộng để quản lý các ứng dụng được đóng gói và các service, giúp thuận lợi trong việc cấu hình và tự động hoá việc triển khai ứng dụng.

   - Trong bài lab này, chúng ta sẽ tạo một **Kubernetes Cluster** đơn giản trên **AWS EKS (Elastic Kubernetes Service)**.
   - Sau đó, mình sẽ triển khai trang web trên cluster và sử dụng **AWS CodePipeLine** để triển khai tự động.

![architecture](/000062_CICDonEKS/images/CI_CDwithAWSCodePipeline.png?width=90pc)

### Content

  1. [Giới thiệu](1-Introduction/)
  2. [Các bước chuẩn bị](2-Preparation-steps/)
  3. [Tạo EKS cluster](3-Create-EKS-cluster/)
  4.  [Tạo Code Pipeline](4-Generate-Code-Pipeline/)
  5.  [Dọn dẹp tài nguyên](5-Clean-up-resources/)