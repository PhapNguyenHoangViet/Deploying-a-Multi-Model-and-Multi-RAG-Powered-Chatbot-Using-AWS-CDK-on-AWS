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

![4-deployment](/images/4-deploy/001-1-deployment.png?width=90pc)


2. Di chuyển vào kho lưu trữ.

```
cd aws-genai-llm-chatbot
```

![4-deployment](/images/4-deploy/002-1-deployment.png?width=90pc)

3. Cài đặt các phụ thuộc của dự án và xây dựng dự án.

```
npm ci && npm run build
```

![4-deployment](/images/4-deploy/003-1-deployment.png?width=90pc)

4. (Tùy chọn) Chạy unit tests
```
npm run test && pip install -r pytest_requirements.txt && pytest tests
```

![4-deployment](/images/4-deploy/004-1-deployment.png?width=90pc)


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

![4-deployment](/images/4-deploy/005-1-deployment.png?width=90pc)

Cấu hình của bạn hiện được lưu trữ trong `bin/config.json`. Bạn có thể chạy lại lệnh `npm run config` khi cần để cập nhật `config.json`.

```
export AWS_ACCESS_KEY_ID=your_aws_access_key_id
export AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
```

![4-deployment](/images/4-deploy/006-1-deployment.png?width=90pc)

```
echo $AWS_ACCESS_KEY_ID
echo $AWS_SECRET_ACCESS_KEY
```

![4-deployment](/images/4-deploy/007-1-deployment.png?width=90pc)


6. Bây giờ bạn có thể triển khai bằng cách chạy:

```
npm run cdk deploy
```

{{% notice note %}}
Thời gian của bước này có thể thay đổi đáng kể(khoảng 45p), tùy thuộc vào các Constructs bạn đang triển khai.
{{% /notice %}}


![4-deployment](/images/4-deploy/010-1-deployment.png?width=90pc)


Bạn có thể xem tiến trình triển khai CDK của mình trong [bảng điều khiển CloudFormation](https://console.aws.amazon.com/cloudformation/home) trong **region** đã chọn.


![4-deployment](/images/4-deploy/008-1-deployment.png?width=90pc)


7. Khi đã triển khai xong, hãy ghi nhớ Giao diện người dùng, Pool người dùng và, nếu bạn muốn tương tác với các nhà cung cấp mô hình bên thứ ba,API_KEYS để truy cập các nhà cung cấp mô hình bên thứ ba.

```
...
Outputs:
GenAIChatBotStack.UserInterfaceUserInterfaceDomanNameXXXXXXXX = dxxxxxxxxxxxxx.cloudfront.net
GenAIChatBotStack.AuthenticationUserPoolLinkXXXXX = https://xxxxx.console.aws.amazon.com/cognito/v2/idp/user-pools/xxxxx_XXXXX/users?region=xxxxx
GenAIChatBotStack.ApiKeysSecretNameXXXX = ApiKeysSecretName-xxxxxx
...
```

8. Mở liên kết **Cognito User Pool** được tạo từ các đầu ra ở trên.


![4-deployment](/images/4-deploy/009-1-deployment.png?width=90pc)

9. Thêm một người dùng sẽ được sử dụng để đăng nhập vào giao diện web.

10. Mở **URL Giao diện** từ các đầu ra ở trên, ví dụ: dxxxxxxxxxxxxx.cloudfront.net.


11. Đăng nhập bằng người dùng đã tạo ở Bước 8 và làm theo hướng dẫn.