+++
title = "Clean up"
date = "`r Sys.Date()`"
weight = 7
chapter = false
pre = "<b>7. </b>"
+++
### Clean up

You can remove the stacks and all the associated resources created in your AWS account by running the following command:

```
npx cdk destroy
```

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/001-11-cleanup.png?width=90pc)



![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/002-11-cleanup.png?width=90pc)

- Enter: `y`

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/003-11-cleanup.png?width=90pc)


{{% notice note %}}
Depending on which resources have been deployed. Destroying the stack might take a while, up to 45m. If the deletion fails multiple times, please manually delete the remaining stack's ENIs; you can filter ENIs by VPC/Subnet/etc using the search bar here in the AWS console) and re-attempt a stack deletion.
{{% /notice %}}


#### **CloudFormation**
  - Find `CloudFormation`
  - Click **CloudFormation**

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/013-11-cleanup.png?width=90pc)

- Click on Delete to Delete **stack CDKToolkit**

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/004-11-cleanup.png?width=90pc)

- **Delete in progress**

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/005-11-cleanup.png?width=90pc)

#### **ECR**
  - Find `ECR`
  - Click **ECR**

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/011-11-cleanup.png?width=90pc)

- **Delete Images** in Repositories(Private registry ECR)
![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/007-11-cleanup.png?width=90pc)

- **Delete Repositories**(Private registry ECR)

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/006-11-cleanup.png?width=90pc)

#### **S3 bucket**
  - Find `S3`
  - Click **S3**

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/012-11-cleanup.png?width=90pc)

- In bucket, empty bucket then delete bucket.

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/008-11-cleanup.png?width=90pc)

#### **EC2 instance**
  - Find `EC2`
  - Click **EC2**

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/010-11-cleanup.png?width=90pc)

- In EC2 intansces, terminate(delete) instance

![11-cleanup](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/11-cleanup/009-11-cleanup.png?width=90pc)
