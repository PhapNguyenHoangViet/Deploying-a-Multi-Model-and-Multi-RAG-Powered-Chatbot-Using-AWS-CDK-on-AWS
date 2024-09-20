+++
title = "Sử dụng Kendra với chỉ mục không phải tiếng Anh"
date = "`r Sys.Date()`"
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++

### Sử dụng Kendra với chỉ mục không phải tiếng Anh

Nếu bạn đang sử dụng Kendra với một chỉ mục bằng ngôn ngữ khác tiếng Anh, bạn sẽ cần thực hiện một số thay đổi trong mã.

Bạn cần sửa đổi các bộ lọc trong tệp `lib/shared/layers/python-sdk/python/genai_core/kendra/query.py`.

Ví dụ cho tiếng Việt:

```
if kendra_index_external or kendra_use_all_data:
    result = kendra.retrieve(
        IndexId=kendra_index_id,
        QueryText=query,
        PageSize=limit,
        PageNumber=1,
        AttributeFilter={'AndAllFilters': [{"EqualsTo": {"Key": "_language_code","Value": {"StringValue": "vi"}}}]}
    )
else:
    result = kendra.retrieve(
        IndexId=kendra_index_id,
        QueryText=query,
        PageSize=limit,
        PageNumber=1,
        AttributeFilter={'AndAllFilters':
            [
                {"EqualsTo": {"Key": "_language_code","Value": {"StringValue": "vi"}}},
                {"EqualsTo": {"Key": "workspace_id","Value": {"StringValue": workspace_id}}}
            ]
        }
    )
```

![7-usingkenra](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/7-usingkenra/001-7-usingkenra.png?width=90pc)

Sau khi thực hiện những thay đổi này, bạn cần phải redeploy giải pháp:
```
npx cdk deploy
```