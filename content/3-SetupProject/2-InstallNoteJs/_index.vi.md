+++  
title = "Cài Đặt NodeJs"  
date = "`r Sys.Date()`"  
weight = 2  
chapter = false  
pre = "<b>3.2. </b>"  
+++  

1. **Cập nhật** danh sách gói trên hệ thống của bạn.

```
sudo apt update
```
- Lệnh này cập nhật danh sách các gói có sẵn và phiên bản của chúng trên hệ thống của bạn. Nó không cài đặt hay nâng cấp bất kỳ gói nào; chỉ làm mới chỉ mục gói.

![installnodejs](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/2-installnodejs/001-2-installnodejs.png?width=90pc)



2. Tải xuống và cài đặt **NVM** **(Node Version Manager)**.
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash
```
- Lệnh này tải xuống và chạy script cài đặt NVM (Node Version Manager) từ GitHub. curl lấy script, và phần | bash chuyển nó tới bash shell để thực thi. NVM cho phép bạn quản lý nhiều phiên bản Node.js trên hệ thống của mình.


![installnodejs](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/2-installnodejs/002-2-installnodejs.png?width=90pc)

3. Áp dụng các thay đổi do **NVM** thực hiện vào phiên làm việc hiện tại của shell.
```
source ~/bashrc
```
- Lệnh này tải lại tệp .bashrc trong thư mục home của bạn để áp dụng các thay đổi được thực hiện bởi script cài đặt NVM. Nó đảm bảo rằng các lệnh của NVM có sẵn trong phiên shell hiện tại của bạn.

- Kiểm tra phiên bản của NVM đã được cài đặt.
```
nvm --version
```
   - Lệnh này kiểm tra và hiển thị phiên bản của NVM để xác minh rằng nó đã được cài đặt đúng cách.

![installnodejs](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/2-installnodejs/003-2-installnodejs.png?width=90pc)

4. Cài đặt **Node.js** phiên bản 18 bằng NVM
```
nvm install 18
```
- Cài đặt Node.js phiên bản 18 bằng NVM. Bạn có thể cài đặt và quản lý nhiều phiên bản Node.js khác nhau với NVM.

![installnodejs](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/2-installnodejs/004-2-installnodejs.png?width=90pc)

5. Hiển thị **the version of NodeJs and the version of npm**.
```
node -v
npm -v
```

![installnodejs](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/2-installnodejs/005-2-installnodejs.png?width=90pc)

6. **Cập nhật**
```
sudo apt update
```

![installnodejs](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/2-installnodejs/006-2-installnodejs.png?width=90pc)