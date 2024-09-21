+++
title = "Triển khai"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++ 
### Triển khai

1. Nhân bản (clone) kho lưu trữ.

```
git clone https://github.com/aws-samples/aws-genai-llm-chatbot
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/001-1-deployment.png?width=90pc)


2. Di chuyển vào kho lưu trữ.

```
cd aws-genai-llm-chatbot
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/002-1-deployment.png?width=90pc)

3. Cài đặt các phụ thuộc của dự án và xây dựng dự án.

```
npm ci && npm run build
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/003-1-deployment.png?width=90pc)

4. (Tùy chọn) Chạy unit tests
- Cài đặt python3
```
sudo apt install python3-pip
```
- Chạy unit tests
```
npm run test && pip install -r pytest_requirements.txt && python3 -m pytest tests
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/004-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/011-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/012-1-deployment.png?width=90pc)


5. Khi hoàn tất, chạy lệnh cấu hình để giúp bạn thiết lập giải pháp với các tính năng bạn cần:

```
npm run config
```

Bạn sẽ được nhắc cấu hình các khía cạnh khác nhau của giải pháp, chẳng hạn như:

- Các LLM hoặc MLM để kích hoạt (chúng tôi hỗ trợ tất cả các mô hình được cung cấp bởi Bedrock mà [**đã được kích hoạt**](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html) cùng với các mô hình được lưu trữ trong SageMaker như Idefics, FalconLite, Mistral và nhiều mô hình khác sẽ được thêm sau).
- Thiết lập hệ thống RAG: lựa chọn động cơ (ví dụ: Aurora với pgvector, OpenSearch, Kendra).
- Lựa chọn embeddings.
- Giới hạn quyền truy cập vào trang web và backend đến VPC (chatbot riêng tư).
- Thêm các chỉ mục Amazon Kendra hiện có làm nguồn RAG.

Khi hoàn tất, hãy trả lời Y để tạo hoặc cập nhật cấu hình của bạn.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/013-1-deployment.png?width=90pc)

Cấu hình của bạn hiện được lưu trữ trong `bin/config.json`. Bạn có thể chạy lại lệnh `npm run config` khi cần để cập nhật `config.json`.


6. Cài đặt **AWS CDK CLI**
Sử dụng **Node Package Manager (npm)** để cài đặt CDK CLI. Chúng tôi khuyến nghị bạn cài đặt nó một cách toàn cầu bằng lệnh sau:
```
npm install -g aws-cdk
```
- **Đặt thông tin xác thực AWS dưới dạng biến môi trường:**

Thay thế your_aws_access_key_id và your_aws_secret_access_key bằng thông tin xác thực AWS thực tế của bạn:
```
export AWS_ACCESS_KEY_ID=your_aws_access_key_id
export AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/006-1-deployment.png?width=90pc)

Các lệnh này sẽ tạm thời đặt thông tin xác thực AWS của bạn trong phiên terminal hiện tại. Chúng cần thiết để xác thực các cuộc gọi từ AWS CLI hoặc SDK trong phiên làm việc.

- **Kiểm tra các biến môi trường:**

Bạn có thể kiểm tra xem các biến đã được đặt đúng hay chưa bằng các lệnh sau:

```
echo $AWS_ACCESS_KEY_ID
echo $AWS_SECRET_ACCESS_KEY
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/007-1-deployment.png?width=90pc)

Điều này sẽ in ra các giá trị của **AWS_ACCESS_KEY_ID** và **AWS_SECRET_ACCESS_KEY** trong terminal để xác nhận rằng chúng đã được đặt thành công.




7. Bây giờ bạn có thể triển khai bằng cách chạy:

```
npm run cdk deploy
```

{{% notice note %}}
Thời gian của bước này có thể thay đổi đáng kể(khoảng 45p), tùy thuộc vào các Constructs bạn đang triển khai.
{{% /notice %}}


![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/010-1-deployment.png?width=90pc)


Bạn có thể xem tiến trình triển khai CDK của mình trong [bảng điều khiển CloudFormation](https://console.aws.amazon.com/cloudformation/home) trong **region** đã chọn.


![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/008-1-deployment.png?width=90pc)


8. Khi đã triển khai xong, hãy ghi nhớ Giao diện người dùng, Pool người dùng và, nếu bạn muốn tương tác với các nhà cung cấp mô hình bên thứ ba,API_KEYS để truy cập các nhà cung cấp mô hình bên thứ ba.

```
...
Outputs:
GenAIChatBotStack.UserInterfaceUserInterfaceDomanNameXXXXXXXX = dxxxxxxxxxxxxx.cloudfront.net
GenAIChatBotStack.AuthenticationUserPoolLinkXXXXX = https://xxxxx.console.aws.amazon.com/cognito/v2/idp/user-pools/xxxxx_XXXXX/users?region=xxxxx
GenAIChatBotStack.ApiKeysSecretNameXXXX = ApiKeysSecretName-xxxxxx
...
```

9. Mở liên kết **Cognito User Pool** được tạo từ các đầu ra ở trên.


![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/009-1-deployment.png?width=90pc)

10. Thêm một người dùng sẽ được sử dụng để đăng nhập vào giao diện web.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/009-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/009-1-deployment.png?width=90pc)

11. Mở **URL Giao diện** từ các đầu ra ở trên, ví dụ: dxxxxxxxxxxxxx.cloudfront.net.
![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/014-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/015-1-deployment.png?width=90pc)

12. Đăng nhập bằng người dùng đã tạo ở Bước 9 và làm theo hướng dẫn.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/016-1-deployment.png?width=90pc)

- Giao diện AWS GenAI Chatbot

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/017-1-deployment.png?width=90pc)