+++
title = "Thiết lập Security Groups"
date = "`r Sys.Date()`"
weight = 3
chapter = false
pre = "<b>2.3. </b>"
+++

Tiếp theo, chúng ta cần bảo mật EC2 Instance.
- Trong phần **Security** của [bảng điều khiển VPC](https://us-east-1.console.aws.amazon.com/vpcconsole/home?region=us-east-1#Home:):
- Chọn **Security groups**
- Nhấn **Create security group**

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/001-3-setupsecuritygroups.png?width=90pc)

Chúng ta sẽ nhập các cài đặt sau cho Security groups của EC2 Instance:
- Tên: `chatbot-ec2-sg`
- Mô tả: `Allow SSH and other private connections`
- VPC: chọn `chatbot-vpc`

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/002-3-setupsecuritygroups.png?width=90pc)

- Trong **Inbound Rules**, thêm một quy tắc:
  - Loại: **SSH**
  - Nguồn: **My IP**

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/003-3-setupsecuritygroups.png?width=90pc)

- **Security groups** đã được tạo

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/004-3-setupsecuritygroups.png?width=90pc)