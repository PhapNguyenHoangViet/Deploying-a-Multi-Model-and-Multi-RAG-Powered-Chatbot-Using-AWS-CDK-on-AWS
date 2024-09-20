+++
title = "AWS GenAI LLM Chatbot"
date = "`r Sys.Date()`"
weight = 1
chapter = false
pre = "<b>1.1. </b>"
+++


**AWS GenAI LLM Chatbot** cung cấp mã nguồn sẵn có để bạn có thể bắt đầu thử nghiệm với nhiều **Mô hình Ngôn Ngữ Lớn** (LLMs) và **Mô hình Ngôn Ngữ Đa Phương Tiện** (MLMs) trong tài khoản AWS của riêng bạn.

![10-testresult](/images/10-testresult/003-10-testresult.png?width=90pc)

### Tính năng
#### Đa mô-đun, toàn diện và sẵn sàng sử dụng
Giải pháp này cung cấp mã nguồn sẵn có để bạn có thể bắt đầu **thử nghiệm với nhiều Mô hình Ngôn Ngữ Lớn và Mô hình Ngôn Ngữ Đa Phương Tiện, cấu hình và gợi ý** trong tài khoản AWS của riêng bạn.

Các nhà cung cấp mô hình được hỗ trợ:

- Amazon Bedrock
- Các mô hình tự lưu trữ trên Amazon SageMaker từ Foundation, Jumpstart và HuggingFace.
- Các nhà cung cấp bên thứ ba qua API như Anthropic, Cohere, AI21 Labs, OpenAI, v.v. Xem các tích hợp langchain có sẵn để có danh sách đầy đủ.

#### Thử nghiệm với các mô hình đa phương tiện
Triển khai các mô hình **IDEFICS** trên **Amazon SageMaker** và xem cách chatbot có thể trả lời câu hỏi về hình ảnh, mô tả nội dung hình ảnh, tạo văn bản dựa trên nhiều hình ảnh.

Ví dụ mẫu

Hiện tại, các mô hình đa phương tiện sau đây được hỗ trợ:

- IDEFICS 9b Instruct
Yêu cầu phiên bản ml.g5.12xlarge.
- IDEFICS 80b Instruct
Yêu cầu phiên bản ml.g5.48xlarge.

Để biết loại phiên bản đúng và cách yêu cầu chúng, hãy đọc yêu cầu của Amazon SageMaker.

{{% notice note %}}
Hãy chắc chắn xem xét các phần giấy phép của các mô hình IDEFICS.
{{% /notice %}}

Để triển khai một mô hình đa phương tiện, hãy làm theo hướng dẫn triển khai và chọn một trong các mô hình được hỗ trợ (nhấn Space để chọn/bỏ chọn) từ bước magic-config CLI và triển khai theo hướng dẫn trong phần trên.

{{% notice note %}}
⚠️ Amazon SageMaker tính phí theo giờ. Hãy chú ý không để mô hình này chạy mà không sử dụng để tránh chi phí không cần thiết.
{{% /notice %}}

#### Trò chuyện Đa Phiên: đánh giá nhiều mô hình cùng lúc
Gửi cùng một truy vấn đến 2 đến 4 mô hình riêng biệt cùng lúc và xem cách mỗi mô hình phản hồi dựa trên lịch sử đã học, ngữ cảnh và quyền truy cập vào cùng một bộ tìm kiếm tài liệu mạnh mẽ, để tất cả các yêu cầu có thể lấy thông tin từ cùng một kiến thức cập nhật.

Ví dụ mẫu

#### Thử nghiệm với nhiều tùy chọn RAG với Workspaces
Một workspace là một không gian tên logic nơi bạn có thể tải lên các tệp để lập chỉ mục và lưu trữ trong một trong các cơ sở dữ liệu vector. Bạn có thể chọn mô hình nhúng và cấu hình phân tách văn bản theo ý muốn.

Ví dụ mẫu

#### Khám phá tiềm năng RAG với Công cụ Gỡ lỗi Workspaces
Giải pháp đi kèm với một số công cụ gỡ lỗi để giúp bạn gỡ lỗi các kịch bản RAG:

Chạy các truy vấn RAG mà không cần chatbot và phân tích kết quả, điểm số, v.v.
Kiểm tra các mô hình nhúng khác nhau trực tiếp trong giao diện người dùng.
Kiểm tra các bộ mã chéo và phân tích khoảng cách giữa các câu khác nhau.
Ví dụ mẫu

#### Giao diện Người dùng Hoàn chỉnh
Kho lưu trữ bao gồm một cấu trúc CDK để triển khai một giao diện người dùng hoàn chỉnh được xây dựng bằng React để tương tác với các LLM/MLM đã triển khai dưới dạng chatbot. Được lưu trữ trên Amazon S3 và phân phối qua [Amazon CloudFront](https://aws.amazon.com/cloudfront/).

Bảo vệ bằng [Xác thực Amazon Cognito](https://aws.amazon.com/cognito/) để giúp bạn tương tác và thử nghiệm với nhiều LLM/MLM, nhiều động cơ RAG, hỗ trợ lịch sử trò chuyện và tải lên/tiến trình tài liệu.

Lớp giao diện giữa giao diện người dùng và backend được xây dựng với [AppSync](https://cloudscape.design/) để quản lý các yêu cầu và tương tác theo thời gian thực với chatbot (tin nhắn và phản hồi) sử dụng các đăng ký GraphQL.

Hệ thống thiết kế được cung cấp bởi [Hệ thống Thiết kế AWS Cloudscape.](https://cloudscape.design/)

### Tài nguyên Bổ sung

| Tài nguyên                                | Mô tả                                                                                                                                                       |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Secure Messenger GenAI Chatbot](https://github.com/aws-samples/secure-messenger-genai-chatbot) | Một ứng dụng nhắn tin được xây dựng trên Wickr có thể giao tiếp với chatbot này để cung cấp dịch vụ Q&A trong các môi trường được quản lý chặt chẽ (ví dụ: HIPAA). |
| [Project Lakechain](https://github.com/awslabs/project-lakechain)             | Một khung xử lý tài liệu (tài liệu, hình ảnh, âm thanh, video) mạnh mẽ, dựa trên đám mây và được AI hỗ trợ, được xây dựng trên AWS CDK.                       |
| [AWS Generative AI CDK Constructs](https://github.com/awslabs/generative-ai-cdk-constructs/) | Thư viện mở rộng mã nguồn mở của [AWS Cloud Development Kit (AWS CDK)](https://docs.aws.amazon.com/cdk/v2/guide/home.html) nhằm giúp các nhà phát triển xây dựng các giải pháp AI sinh sản sử dụng các định nghĩa dựa trên mẫu cho kiến trúc của họ. |
| [Artifacts and Tools for Bedrock](https://github.com/aws-samples/artifacts-and-tools-for-bedrock) | Một giao diện người dùng dựa trên trò chuyện đổi mới với hỗ trợ cho các công cụ và tài liệu. Nó có thể tạo đồ thị và sơ đồ, phân tích dữ liệu, viết bài, tạo trang web, tạo tệp và nhiều hơn nữa. |