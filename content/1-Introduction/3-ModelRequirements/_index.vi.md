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

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/001-3-modelrequirements.png?width=90pc)

- Chọn **Model access**
- Chọn **Enable all models**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/002-3-modelrequirements.png?width=90pc)

- Chọn **next**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/003-3-modelrequirements.png?width=90pc)

- Chọn **Submit**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/004-3-modelrequirements.png?width=90pc)

- **Amazon Bedrock**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/005-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/006-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/007-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/008-3-modelrequirements.png?width=90pc)

#### Xác thực HuggingFace

Một số mô hình được lưu trữ trên HuggingFace yêu cầu khóa API để truy cập. Ví dụ, các mô hình từ MistralAI và Meta hiện đã yêu cầu bạn phải chấp nhận EULA của họ để có thể sử dụng.

Nếu bạn muốn tiếp tục sử dụng các mô hình này hoặc truy cập các mô hình khác trên HuggingFace mà yêu cầu xác thực, bạn có thể cung cấp access tokens HF (HuggingFace) như một phần của trình cài đặt.

Khi bạn kích hoạt các mô hình SageMaker trong trình cài đặt, nó sẽ yêu cầu bạn cung cấp ARN của bí mật trong AWS Secrets Manager chứa access tokens HF.

Bạn có thể đọc thêm về cách thiết lập access tokens truy cập trên [trang web của HuggingFace](https://huggingface.co/docs/hub/en/security-tokens). Sau khi có access tokens, bạn có thể cần truy cập vào trang của mô hình, chẳng hạn như `mistral7B`, để chấp nhận các điều khoản trước khi sử dụng access tokens để truy cập mô hình.

Bí mật bạn tạo trong Secrets Manager sẽ là một bí mật dạng văn bản thuần, chỉ chứa access tokens HF.

Việc xác thực này là cần thiết để đảm bảo bạn có quyền truy cập vào các mô hình yêu cầu xác thực và để bảo vệ các điều khoản sử dụng của nhà cung cấp mô hình.

1. Đăng ký hoặc Đăng nhập tài khoản HuggingFace
   - Truy cập [HuggingFace](https://huggingface.co/).
   - Nếu bạn chưa có tài khoản, hãy Đăng ký bằng cách bấm vào nút "Sign Up". Nếu đã có tài khoản, hãy bấm vào "Login" và nhập thông tin để Đăng nhập.

2. Lấy access tokens API từ HuggingFace
   - Sau khi đăng nhập, vào Trang cá nhân bằng cách nhấp vào ảnh đại diện của bạn ở góc trên bên phải, sau đó chọn Settings (Cài đặt).
   - Ở cột bên trái, chọn Access Tokens (Mã truy cập).
   Tại đây, bạn sẽ thấy một nút New Token (Tạo mã mới). Bấm vào nút này để tạo access tokens truy cập API mới.
   - Đặt tên cho access tokens của bạn và chọn quyền truy cập là Read (Chỉ đọc), sau đó bấm Generate (Tạo mã).
   - Sao chép access tokens API này, vì bạn sẽ cần sử dụng nó ở các bước tiếp theo.

3. Chấp nhận Điều khoản sử dụng Mô hình (nếu có)
   - Để sử dụng các mô hình bị hạn chế như mistral7B hoặc các mô hình Meta, bạn cần chấp nhận EULA của mô hình.
   - Truy cập vào trang mô hình mà bạn muốn sử dụng (ví dụ: mistral7B).
   - Cuộn xuống phần Model Card và nếu mô hình yêu cầu, bạn sẽ thấy một nút để chấp nhận các điều khoản và điều kiện.
   - Bấm vào nút Accept để chấp nhận các điều khoản và cho phép access tokens của bạn truy cập vào mô hình.
     
4. Tạo Bí mật API trong AWS Secrets Manager
   - Truy cập AWS Secrets Manager trong bảng điều khiển AWS.
   - Nhấn Store a new secret (Lưu trữ bí mật mới).
   - Chọn Other type of secrets (Loại bí mật khác) và nhập access tokens HF của bạn vào dưới dạng văn bản thuần (Plaintext).
   - Đặt tên cho bí mật, ví dụ: HuggingFace-Token và lưu trữ nó.
   - Lưu lại ARN bí mật từ Secrets Manager vì bạn sẽ sử dụng ARN này để cung cấp access tokens cho Amazon SageMaker.


#### Yêu cầu cho mô hình của bên thứ ba

Bạn cũng có thể tương tác với các nhà cung cấp bên ngoài thông qua API của họ, chẳng hạn như AI21 Labs, Cohere, OpenAI,...

Nhà cung cấp phải được hỗ trợ trong [Model Interface](https://github.com/aws-samples/aws-genai-llm-chatbot/blob/main/lib/model-interfaces/langchain/functions/request-handler/index.py), [ xem danh sách tích hợp langchain có sẵn](https://python.langchain.com/docs/integrations/llms/) để biết danh sách toàn diện các nhà cung cấp.

Thông thường, một **API_KEY** là cần thiết để tích hợp với các mô hình bên thứ ba. Để làm điều này, [Model Interface](https://github.com/aws-samples/aws-genai-llm-chatbot/blob/main/lib/model-interfaces/langchain/index.ts)  sẽ triển khai một **Secrets** trong [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/), ban đầu với một JSON rỗng {}, nơi bạn có thể thêm các API KEY một hoặc nhiều nhà cung cấp.

Các khóa này sẽ được tiêm vào runtime vào các Biến Môi trường của chức năng Lambda; chúng sẽ không hiển thị trong AWS Lambda Console.

Ví dụ, nếu bạn muốn có khả năng tương tác với AI21 Labs, OpenAI và Cohere endpoints:

- Mở [Model Interface Keys Secret](https://github.com/aws-samples/aws-genai-llm-chatbot/blob/main/lib/model-interfaces/langchain/index.ts#L38) trong Secrets Manager. Bạn cũng có thể tìm thấy tên **Secrets** trong đầu ra của stack.
- Cập nhật **Secrets** bằng cách thêm một khóa vào JSON

```json
{
  "AI21_API_KEY": "xxxxx",
  "OPENAI_API_KEY": "sk-xxxxxxxxxxxxxxx",
  "COHERE_API_KEY": "xxxxx"
}
```

{{% notice note %}}
Trong trường hợp không cần khóa, giá trị bí mật phải là một JSON rỗng `{}`, KHÔNG phải là một chuỗi rỗng `''`.
{{% /notice %}}


Hãy chắc chắn rằng biến môi trường phù hợp với những gì được yêu cầu bởi khung làm việc đang sử dụng, như Langchain (xem danh sách tích hợp langchain có sẵn).

#### Tích hợp Azure OpenAI như mô hình bên thứ ba

- Mở bí mật SharedApiKeysSecretxyz trong Secrets Manager
- Cập nhật các Bí mật bằng cách thêm các khóa sau vào JSON (hoặc Key/values):

```
{
  "AZURE_OPENAI_MODELS": "Model1,Model2",
  "AZURE_OPENAI_API_TYPE__Model1": "azure",
  "AZURE_OPENAI_API_VERSION__Model1": "2023-05-15",
  "AZURE_OPENAI_API_BASE__Model1": "https://model1.openai.azure.com/",
  "AZURE_OPENAI_API_KEY__Model1": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "AZURE_OPENAI_API_DEPLOYMENT_NAME__Model1": "Model1DeploymentName",
  "AZURE_OPENAI_API_TYPE__Model2": "azure",
  "AZURE_OPENAI_API_VERSION__Model2": "2023-07-01-preview",
  "AZURE_OPENAI_API_BASE__Model2": "https://model2.openai.azure.com/",
  "AZURE_OPENAI_API_KEY__Model2": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "AZURE_OPENAI_API_DEPLOYMENT_NAME__Model2": "Model2DeploymentName"
}
```
Ở đây, chúng ta tích hợp 2 mô hình khác: Model1 và Model2. Đối với mỗi mô hình, chúng ta cần xác định các thông tin sau mà bạn sẽ lấy từ tenant Azure OpenAI của mình. ${ModelIdentifier} có thể là Model1 hoặc Model2:
 * `AZURE_OPENAI_API_TYPE__${ModelIdentifier}`
 * `AZURE_OPENAI_API_VERSION__${ModelIdentifier}`
 * `AZURE_OPENAI_API_BASE__${ModelIdentifier}`
 * `AZURE_OPENAI_API_KEY__${ModelIdentifier}`
 * `AZURE_OPENAI_API_DEPLOYMENT_NAME__${ModelIdentifier}`