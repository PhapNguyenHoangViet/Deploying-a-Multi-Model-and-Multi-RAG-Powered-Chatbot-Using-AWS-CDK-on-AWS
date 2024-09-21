+++
title = "Chạy giao diện người dùng cục bộ"
date = "`r Sys.Date()`"
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++

#### Chạy giao diện người dùng cục bộ

Bạn có thể chạy ứng dụng react Vite này cục bộ theo các bước sau.

#### Tùy chọn 1: Cấu hình môi trường

Lấy tệp `aws-exports.json` từ điểm cuối phân phối CloudFront mà bạn nhận được từ đầu ra CDK và lưu nó vào thư mục `./lib/user-interface/react-app/public/`. Sau đó chạy `npm run dev`.

Ví dụ:

```
cd lib/user-interface/react-app/public
curl -O https://dxxxxxxxxxxxx.cloudfront.net/aws-exports.json
cd ..
npm run dev
```
![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/018-1-deployment.png?width=90pc)


#### Tùy chọn 2: Đặt cấu hình dưới dạng biến môi trường

```
export AWS_PROJECT_REGION="..."
export AWS_COGNITO_REGION="..."
export AWS_USER_POOLS_ID="..."
export AWS_USER_POOLS_WEB_CLIENT_ID="..."
export API_DISTRIBUTION_DOMAIN_NAME="..."
export RAG_ENABLED=1|0
export DEFAULT_EMBEDDINGS_MODEL="..."
export DEFAULT_CROSS_ENCODER_MODEL="..."
npm run build:dev
npm run dev
```

**Đăng nhập bằng người dùng đã tạo**

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/019-1-deployment.png?width=90pc)

- AWS GenAI Chatbot

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/020-1-deployment.png?width=90pc)