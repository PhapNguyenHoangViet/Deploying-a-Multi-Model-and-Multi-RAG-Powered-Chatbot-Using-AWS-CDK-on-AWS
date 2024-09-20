+++
title = "Dọn dẹp"
date = "`r Sys.Date()`"
weight = 7
chapter = false
pre = "<b>7. </b>"
+++

### Dọn dẹp

Bạn có thể xóa các stack và tất cả các tài nguyên liên quan đã được tạo trong tài khoản AWS của bạn bằng cách chạy lệnh sau:
```
npx cdk destroy
```

![11-cleanup](/images/11-cleanup/001-11-cleanup.png?width=90pc)

![11-cleanup](/images/11-cleanup/002-11-cleanup.png?width=90pc)

- Nhập: `y`

![11-cleanup](/images/11-cleanup/003-11-cleanup.png?width=90pc)

{{% notice note %}}
Tùy thuộc vào các tài nguyên đã được triển khai, việc xóa stack có thể mất một thời gian, lên đến 45 phút. Nếu việc xóa thất bại nhiều lần, hãy xóa thủ công các ENI còn lại của stack; bạn có thể lọc ENI theo VPC/Subnet/v.v. bằng cách sử dụng thanh tìm kiếm trong bảng điều khiển AWS.
{{% /notice %}}

#### **CloudFormation**
- Tìm `CloudFormation`
- Nhấp vào **CloudFormation**

![11-cleanup](/images/11-cleanup/013-11-cleanup.png?width=90pc)

- Nhấp vào Xóa để xóa **stack CDKToolkit**

![11-cleanup](/images/11-cleanup/004-11-cleanup.png?width=90pc)

- **Đang xóa**

![11-cleanup](/images/11-cleanup/005-11-cleanup.png?width=90pc)

#### **ECR**
- Tìm `ECR`
- Nhấp vào **ECR**

![11-cleanup](/images/11-cleanup/011-11-cleanup.png?width=90pc)

- **Xóa hình ảnh** trong các kho chứa (Private registry ECR)

![11-cleanup](/images/11-cleanup/007-11-cleanup.png?width=90pc)

- **Xóa các kho chứa** (Private registry ECR)

![11-cleanup](/images/11-cleanup/006-11-cleanup.png?width=90pc)

#### **S3 bucket**
- Tìm `S3`
- Nhấp vào **S3**

![11-cleanup](/images/11-cleanup/012-11-cleanup.png?width=90pc)

- Trong kho chứa, xóa nội dung kho chứa rồi xóa kho chứa.

![11-cleanup](/images/11-cleanup/008-11-cleanup.png?width=90pc)

#### **EC2 instance**
- Tìm `EC2`
- Nhấp vào **EC2**

![11-cleanup](/images/11-cleanup/010-11-cleanup.png?width=90pc)

- Trong các phiên bản EC2, kết thúc (xóa) phiên bản.

![11-cleanup](/images/11-cleanup/009-11-cleanup.png?width=90pc)
