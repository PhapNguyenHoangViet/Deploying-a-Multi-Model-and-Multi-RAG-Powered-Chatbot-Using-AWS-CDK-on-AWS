+++
title = "Khởi tạo EC2 Instance"
date = "`r Sys.Date()`"
weight = 4
chapter = false
pre = "<b>2.4. </b>"
+++

### Khởi tạo EC2 Instance

1. Truy cập vào [AWS Management Console](https://aws.amazon.com/console/)

   - Tìm **EC2**
   - Chọn **EC2**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/001-4-launchec2instance.png?width=90pc)

2. Trong giao diện **EC2**

   - Chọn **Instances**
   - Chọn **Launch instances**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/002-4-launchec2instance.png?width=90pc)

3. Đặt tên, nhập `Chatbot-ec2`

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/003-4-launchec2instance.png?width=90pc)

4. Chọn **AMI**

   - Chọn **Quick Start**
   - Chọn **Ubuntu**
   - Amazon Machine Image (AMI): Ubuntu Server 22.04 LTS (HVM), SSD Volume Type
   - Kiến trúc: 64-bit (x86)

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/004-4-launchec2instance.png?width=90pc)

5. Chọn **Loại phiên bản**

   - Chọn **m5.large** hoặc loại lớn hơn.

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/005-4-launchec2instance.png?width=90pc)

- Chọn **Tạo mới key pair**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/006-4-launchec2instance.png?width=90pc)

6. Cấu hình **key pair**.

   - Tên key pair: `chatbot-keypair`
   - Loại key pair: **RSA**
   - Định dạng file private key: **.pem**
   - **Tạo key pair**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/007-4-launchec2instance.png?width=90pc)

7. Cấu hình **Network**

   - **VPC**, chọn VPC đã tạo.
   - **Subnet**, chọn **Public subnet**
   - Kiểm tra **Auto-assign public IP**? Nếu bạn chưa xem xét bước cấp IP công cộng trong bước tạo VPC.
   - Chọn **Existing security group** và chọn `chatbot-ec2-sg`

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/008-4-launchec2instance.png?width=90pc)

8. Cấu hình **Storage**

   - **100 GiB**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/009-4-launchec2instance.png?width=90pc)

9. Chọn **Launch instance**

10. Khởi tạo thành công và chọn **View all instances**
