+++
title = "Tạo IAM User"
date = "`r Sys.Date()`"
weight = 1
chapter = false
pre = "<b>2.1. </b>"
+++

#### Tạo IAM User

1. Đăng nhập vào [IAM console](https://console.aws.amazon.com/iam/home#/home)

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/001-1-creatingiamuser.png?width=90pc)

2. Trong thanh điều hướng bên trái, chọn **User**, sau đó nhấp vào **Add User**

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/002-1-creatingiamuser.png?width=90pc)

3. Tại trang **Set user details**, nhập các thông tin sau:
    - Tên người dùng: **Chatbot-user**
    - Loại quyền truy cập: đánh dấu vào **AWS Management Console access** để cho phép người dùng truy cập bảng điều khiển AWS
    - Mật khẩu bảng điều khiển: chọn **Custom password** và nhập mật khẩu mà bạn muốn cho người dùng
    - Yêu cầu đặt lại mật khẩu: bỏ chọn tùy chọn này để người dùng không cần thay đổi mật khẩu khi đăng nhập lần đầu
    - Kiểm tra và chọn **Next: Permissions**

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/003-1-creatingiamuser.png?width=90pc)
![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/004-1-creatingiamuser.png?width=90pc)

4. Tại trang **Set permissions**, thực hiện:
- Chọn **Attach existing policies directly** để chọn phương thức cấp quyền trực tiếp cho người dùng.

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/005-1-creatingiamuser.png?width=90pc)

- Một người dùng IAM với chính sách **AdministratorAccess** được cấp quyền (đối với sản xuất, chúng tôi khuyên bạn nên hạn chế quyền truy cập theo nhu cầu)

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/006-1-creatingiamuser.png?width=90pc)

5. Tại trang Add tags (optional), giữ nguyên mặc định và chọn **Next: Review**

6. Tại trang **Xem lại**, kiểm tra thông tin và chọn **Tạo người dùng**

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/007-1-creatingiamuser.png?width=90pc)

7. Khi khởi tạo hoàn tất, nhấn **Close** để trở lại  **IAM Console**.

8. Kích hoạt **MFA**

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/008-1-creatingiamuser.png?width=90pc)

- Kích hoạt với MFA
- Tạo khóa truy cập

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/009-1-creatingiamuser.png?width=90pc)

9. Tạo **access key**

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/011-1-creatingiamuser.png?width=90pc)

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/012-1-creatingiamuser.png?width=90pc)

   - Tải xuống tệp .csv
   - Hoàn tất

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/013-1-creatingiamuser.png?width=90pc)

10. Đã tạo xong **IAM User**

![creatingiamuser](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/1-creatingiamuser/014-1-creatingiamuser.png?width=90pc)