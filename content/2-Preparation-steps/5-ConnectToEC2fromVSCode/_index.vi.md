+++
title = "Kết nối với EC2 Instance từ VSCode"
date = "`r Sys.Date()`"
weight = 5
chapter = false
pre = "<b>2.5. </b>"
+++

Kết nối qua SSH từ Visual Studio Code đến một EC2 Instance là một lựa chọn nhanh chóng thay thế cho Cloud9.

### Tải Visual Studio Code và cài đặt Remote - SSH extension
Bạn có thể tải VS Code tại đây: [Tải VSCode](https://code.visualstudio.com/download)

Sau khi tải xuống, hãy cài đặt Remote - SSH extension.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/001-5-connecttoec2fromvscode.png?width=90pc)

- Nhấp vào **Connect to Host.**

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/002-5-connecttoec2fromvscode.png?width=90pc)

- Nhấp vào **Add New SSH Host.**

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/003-5-connecttoec2fromvscode.png?width=90pc)

- Trong hộp nhập liệu, nhập `chatbot-ec2` và nhấn Enter.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/004-5-connecttoec2fromvscode.png?width=90pc)

- Nhấp vào đường dẫn C:\Users\vietp.ssh\config để cấu hình.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/005-5-connecttoec2fromvscode.png?width=90pc)

- Nhấp vào **Open Config**.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/006-5-connecttoec2fromvscode.png?width=90pc)

- Trong khối cấu hình SSH, thay thế các giá trị placeholder bằng địa chỉ IPv4 chính xác của EC2 Instance và đường dẫn đến Key Pair trên máy tính của bạn.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/007-5-connecttoec2fromvscode.png?width=90pc)

- Nhấp vào **Connect to Host.**

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/008-5-connecttoec2fromvscode.png?width=90pc)

- Nhấp vào biểu tượng SSH ở góc dưới bên trái để bắt đầu quá trình kết nối.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/009-5-connecttoec2fromvscode.png?width=90pc)

- Chọn **Linux** và chờ một chút để VSCode Server được cài đặt trên EC2 Instance.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/0010-5-connecttoec2fromvscode.png?width=90pc)

- Chọn **Open Folder** và nhấp **OK**.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/0011-5-connecttoec2fromvscode.png?width=90pc)

- Đây là giao diện sau khi kết nối thành công.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/0012-5-connecttoec2fromvscode.png?width=90pc)
