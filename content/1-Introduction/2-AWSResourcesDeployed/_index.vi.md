+++
title = "Tổng quan Tài nguyên AWS"
date = 2024
weight = 2
chapter = false
pre = "<b>1.2. </b>"
+++

### Tổng quan

Giải pháp có thể cấu hình để triển khai một loạt tài nguyên, không phải tất cả tài nguyên được mô tả trong danh sách đều có thể áp dụng cho việc triển khai của bạn.

Khuyến nghị xem xét để hiểu các cấu hình triển khai, an ninh và ảnh hưởng về chi phí, cũng như các thực hành tốt nhất tổng thể.

![kiến trúc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/architecture1.png?width=90pc)

{{% notice note %}}
Danh sách này được coi là một cách tiếp cận tốt nhất để giúp bạn hiểu các tài nguyên trong môi trường của mình và có thể không bao quát tất cả. Hãy đảm bảo bạn xem xét giải pháp và xác thực yêu cầu trước khi triển khai.
{{% /notice %}}

---

### Authentication
**Amazon Cognito**

User Pool [Bắt buộc]

User Pool Client [Bắt buộc]
  - Gắn một miền Cognito hiện có cho Liên kết, thêm quyền cho User Pool để tận dụng miền Cognito hiện có / Tạo nhà cung cấp danh tính OIDC hoặc SAML trong Cognito [Tùy chọn]

---

### Retrieval Augmented Generation (RAG) Engines
Phần này mô tả các động cơ RAG chứa và trả dữ liệu đã lưu để sử dụng với AI sinh sản. Thêm vào đó, phần này bao gồm các tài nguyên được triển khai để hỗ trợ việc nạp dữ liệu và xử lý cho RAG.

#### Amazon Aurora PostgreSQL
- **RAG Workspaces**: Nếu tùy chọn này được bật, người dùng có thể tạo kho dữ liệu PostgreSQL với pgvector cho các không gian làm việc Tăng cường Tìm kiếm (RAG). [Tùy chọn]

{{% notice note %}}
Tùy chọn này không được bật theo mặc định, người dùng phải chọn bật nó trong cấu hình trước khi triển khai.
{{% /notice %}}

#### Amazon OpenSearch Serverless Service
**RAG Workspaces**: Nếu tùy chọn này được bật, người dùng có thể tạo Các Bộ sưu tập OpenSearch Serverless cho các không gian làm việc Tăng cường Tìm kiếm (RAG). [Tùy chọn]
{{% notice note %}}
Tùy chọn này không được bật theo mặc định, người dùng phải chọn bật nó trong cấu hình trước khi triển khai.
{{% /notice %}}

#### Amazon Kendra
**RAG Workspaces**: Nếu tùy chọn này được bật, người dùng có thể tạo kho dữ liệu Kendra cho các không gian làm việc Tăng cường Tìm kiếm (RAG). [Tùy chọn]
{{% notice note %}}
Tùy chọn này không được bật theo mặc định, người dùng phải chọn bật nó trong cấu hình trước khi triển khai.
{{% /notice %}}

#### Amazon Simple Storage Service (S3)
**File Uploads Bucket:** Các tệp được tải lên trong các không gian làm việc RAG [Bắt buộc]

**Processing Bucket:** Bucket để chứa các tệp đang được xử lý cho một không gian làm việc RAG [Bắt buộc]

#### DynamoDB
**WorkSpaces Table:** Bảng chứa dữ liệu về các không gian làm việc RAG. Không chứa dữ liệu RAG thực tế, mà chỉ chứa dữ liệu siêu dữ liệu/cấu hình cho không gian làm việc. [Bắt buộc]

**Documents Table:** Bảng chứa dữ liệu về các tài liệu đã được hoặc cần được nạp vào các không gian làm việc RAG (các trang web, PDF, tệp văn bản, RSS feeds, v.v.) [Bắt buộc]

#### Step Functions

**File Import Workflow:** State Machine chịu trách nhiệm xử lý quy trình nạp tệp [Bắt buộc]

**Website Crawling Workflow:** State Machine chịu trách nhiệm xử lý quy trình thu thập dữ liệu từ trang web [Bắt buộc]

**Delete Workspace Workflow:** State Machine chịu trách nhiệm xử lý việc xóa không gian làm việc RAG (gỡ bỏ tài nguyên liên quan đến không gian làm việc RAG) [Bắt buộc]

**Delete Document Workflow:** State Machine chịu trách nhiệm xử lý việc xóa tài liệu trong không gian làm việc RAG [Bắt buộc]

#### Amazon Batch
**Website Crawler Batch Job:** Thực hiện một tác vụ batch chạy trong một EC2 Instance trong một ECS Container để xử lý quy trình thu thập dữ liệu từ trang web. Instance sẽ được hủy khi không có xử lý đang hoạt động.

**File Import Batch Job:** Thực hiện một tác vụ batch chạy trong một EC2 Instance trong một ECS Container để xử lý quy trình nạp tệp. Instance sẽ được hủy khi không có xử lý đang hoạt động.

#### Amazon Simple Queue Service (SQS)
**Ingestion Queue:** Hàng đợi nhận những gì cần nạp và được xử lý ở phía hạ lưu. [Bắt buộc]

#### Lambda Functions
**RSS Ingestor:** Lambda Function chịu trách nhiệm lấy dữ liệu mới nhất từ RSS Feed, xếp hàng các bài đăng mới [Bắt buộc]

**Trigger RSS Ingestors Function:** Kích hoạt hàm RSS Ingestor cho mỗi RSS Feed có đăng ký được bật trong không gian làm việc. [Bắt buộc]
{{% notice note %}}
Được kích hoạt bởi một Quy tắc EventBridge để thực hiện theo Tỷ lệ cố định
{{% /notice %}}

**Crawl Queued RSS Posts Function:** Lambda Function chịu trách nhiệm kích hoạt quy trình thu thập dữ liệu từ trang web cho mỗi bài đăng RSS cần nạp [Bắt buộc]
{{% notice note %}}
Được kích hoạt bởi một Quy tắc EventBridge để thực hiện theo Tỷ lệ cố định
{{% /notice %}}

**Upload Handler Function:** Hàm chịu trách nhiệm xử lý các tệp tải lên [Bắt buộc]

---

### Chatbot API

#### DynamoDB
**Session Table:** Chứa các phiên chat của người dùng với chatbot [Bắt buộc]

#### Amazon Simple Storage Service (S3)
**Logs Bucket:** Chứa nhật ký cho Chatbot API [Bắt buộc]

**Files Bucket:** Chứa các tệp được tải lên trong quá trình chat với chatbot [Bắt buộc]

**User Feedback Bucket:** Chứa dữ liệu từ phản hồi của người dùng khi chat với chatbot và chọn cung cấp phản hồi. [Bắt buộc]

#### Amazon Simple Notification Service (SNS)
**Messages Topic:** Chủ đề để quản lý bus tin nhắn [Bắt buộc]

#### Amazon Simple Queue Service (SQS)
**Outgoing Messages Queue:** Hàng đợi để quản lý các tin nhắn đi [Bắt buộc]

**Outgoing Messages Dead-Letter Queue (DLQ)**: Hàng đợi để xử lý các tin nhắn Dead-Letter từ Hàng đợi Tin nhắn Đi [Bắt buộc]

#### AWS Lambda Functions
**AppSync GraphQL API Handler:** Hàm chịu trách nhiệm xử lý tất cả các yêu cầu API GraphQL đầu vào và xử lý chúng. [Bắt buộc]

{{% notice note %}}
Trình xử lý API AppSync hoạt động như một lambda duy nhất cho tất cả các yêu cầu API. Điều này có nghĩa là hàm này có một tập hợp quyền khá rộng để tương tác với cơ sở dữ liệu, kho dữ liệu, các dịch vụ AWS, v.v.
{{% /notice %}}

#### AppSync
**GraphQL API:** API chính cho ứng dụng, bao gồm cả Streaming Thời gian Thực cho Chatbot và API Rest cho dữ liệu. [Bắt buộc]

{{% notice note %}}
Tùy chọn thiết lập GraphQL để riêng tư, trong một VPC và không được công khai ra Internet.
Các Trình xử lý API GraphQL có quyền gọi các hàm/điểm cuối đã xác định của chúng.
{{% /notice %}}

---

### Giao diện Người dùng

#### Amazon Simple Storage Service (S3)
**Upload Logs Bucket:** Bucket mà nhật ký từ các lần tải lên của người dùng được lưu trữ [Bắt buộc]

**Website Bucket:** Bucket chứa giao diện người dùng dựa trên React [Bắt buộc]

#### Amazon CloudFront
**Front-End Distribution:** CDN công khai phục vụ nội dung trang web từ Website Bucket. [Tùy chọn, mặc định đã bao gồm]

- {{% notice note %}}
Theo mặc định, giải pháp được cấu hình là công khai với một Phân phối CloudFront. Trong cấu hình trước khi triển khai, giải pháp có thể được triển khai bên trong một VPC như một trang web riêng tư.
{{% /notice %}}

- "Công khai" đề cập đến khả năng truy cập của trang web, không phải khả năng đăng nhập. Một trang web công khai sử dụng Amazon Cognito như đã mô tả trong phần Xác thực.

#### VPC, Cân bằng tải và Mạng
**Cấu hình Trang web Riêng tư:** Giải pháp có thể được triển khai như một trang web riêng tư, với quyền truy cập bên ngoài bị hạn chế. Trong cấu hình trước khi triển khai, giải pháp có thể được triển khai bên trong một VPC bằng cách triển khai một **Cân bằng tải Ứng dụng** bên trong **VPC**. Điều này cũng định tuyến lưu lượng truy cập giữa các dịch vụ thông qua các Điểm cuối VPC (ví dụ: truy cập S3) [Tùy chọn, thay thế cho việc triển khai CloudFront]

---

### Mô hình & Điểm cuối ML
Lưu ý: Trong cấu hình trước khi triển khai, có một loạt các cấu hình có thể áp dụng để tùy chỉnh việc sử dụng mô hình để đáp ứng các nhu cầu cụ thể. Có việc sử dụng mô hình liên quan đến suy diễn và nhúng văn bản.

#### Bedrock
**Truy cập Mô hình Chung:** Truy cập chung đến tất cả các mô hình Bedrock được kích hoạt trong tài khoản/khu vực. [Tùy chọn]
Truy cập Bedrock có thể bị vô hiệu hóa (không được kích hoạt) thông qua quá trình cấu hình trước khi triển khai.
**Truy cập Mô hình Hạn chế:** Nếu Bedrock được kích hoạt, một ARN vai trò IAM có thể được cung cấp để thiết lập quyền tùy chỉnh. Đây là lựa chọn thay thế cho Truy cập Mô hình Chung. [Tùy chọn]

#### SageMaker

**Mô hình đã Triển khai:** Truy cập vào các mô hình triển khai. Điều này có thể tùy chỉnh trong cấu hình trước khi triển khai và có thể khác nhau tùy thuộc vào các thiết lập được áp dụng. [Tùy chọn]

---
{{% notice note %}}
Danh sách này không bao gồm chi tiết về các quyền IAM cần thiết cho hoạt động của giải pháp vì nhiều quyền phụ thuộc vào các cấu hình trước khi triển khai.
{{% /notice %}}
