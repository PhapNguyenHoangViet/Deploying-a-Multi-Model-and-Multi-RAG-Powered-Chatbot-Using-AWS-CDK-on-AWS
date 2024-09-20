+++
title = "Yêu cầu về Mô hình"
date = 2024
weight = 3
chapter = false
pre = "<b>1.3. </b>"
+++

#### Yêu cầu Amazon SageMaker (chỉ dành cho self-hosted models) [](https://aws-samples.github.io/aws-genai-llm-chatbot/documentation/model-requirements.html#amazon-sagemaker-requirements-for-self-hosted-models-only)


Nếu bạn đang tìm cách tự lưu trữ các mô hình trên Amazon SageMaker, bạn có thể cần yêu cầu tăng hạn ngạch dịch vụ cho các loại phiên bản SageMaker cụ thể, chẳng hạn như loại phiên bản `ml.g5`. Điều này sẽ cho phép bạn truy cập các loại phiên bản GPU/Multi-GPU thế hệ mới nhất. [Bạn có thể làm điều này từ bảng điều khiển AWS](https://console.aws.amazon.com/servicequotas/home/services/sagemaker/quotas).

#### Yêu cầu Amazon Bedrock [](https://aws-samples.github.io/aws-genai-llm-chatbot/documentation/model-requirements.html#amazon-bedrock-requirements)

**Truy cập Mô hình Cơ bản**

Nếu bạn muốn tương tác với các mô hình từ Amazon Bedrock, bạn cần [yêu cầu truy cập](https://console.aws.amazon.com/bedrock/home?#/modelaccess) vào các mô hình cơ bản trong một trong những khu vực mà Amazon Bedrock có sẵn. Đảm bảo đọc và chấp nhận các thỏa thuận giấy phép người dùng cuối hoặc EULA của các mô hình.

{{% notice note %}}
Bạn có thể triển khai giải pháp ở một khu vực khác với nơi bạn đã yêu cầu truy cập Mô hình Cơ bản.
**Trong khi việc phê duyệt truy cập Mô hình Cơ bản là ngay lập tức, có thể mất vài phút để có được quyền truy cập và thấy danh sách các mô hình trong giao diện người dùng.**
{{% /notice %}}

- Tìm **Bedrock**
- Chọn **Bedrock**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/001-3-modelrequirements.png?width=90pc)

- Chọn **Model access**
- Chọn **Enable all models**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/002-3-modelrequirements.png?width=90pc)

- Chọn **next**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/003-3-modelrequirements.png?width=90pc)

- Chọn **Submit**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/004-3-modelrequirements.png?width=90pc)

- **Amazon Bedrock**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/005-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/images/1-introduction/3-modelrequirements/006-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/images/1-introduction/3-modelrequirements/007-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/images/1-introduction/3-modelrequirements/008-3-modelrequirements.png?width=90pc)
