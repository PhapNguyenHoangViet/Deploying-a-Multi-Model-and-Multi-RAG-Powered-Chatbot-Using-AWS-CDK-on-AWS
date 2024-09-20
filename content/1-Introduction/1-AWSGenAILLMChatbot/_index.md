+++
title = "AWS GenAI LLM Chatbot"
date = "`r Sys.Date()`"
weight = 1
chapter = false
pre = "<b>1.1. </b>"
+++


The **AWS GenAI LLM Chatbot** provides ready-to-use code so you can start experimenting with a variety of **Large Language Models** and **Multimodal Language Models**, settings and prompts in your own AWS account.

![10-testresult](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/10-testresult/003-10-testresult.png?width=90pc)

### **Features**
### Modular, comprehensive and ready to use
This solution provides ready-to-use code so you can start **experimenting with a variety of Large Language Models and Multimodal Language Models, settings and prompts** in your own AWS account.

Supported model providers:

- Amazon Bedrock
- Amazon SageMaker self-hosted models from Foundation, Jumpstart and HuggingFace.
- Third-party providers via API such as Anthropic, Cohere, AI21 Labs, OpenAI, etc. See available langchain integrations for a comprehensive list.

### Experiment with multimodal models
Deploy **IDEFICS** models on **Amazon SageMaker** and see how the chatbot can answer questions about images, describe visual content, generate text grounded in multiple images.

sample

Currently, the following multimodal models are supported:

- IDEFICS 9b Instruct
Requires ml.g5.12xlarge instance.
- IDEFICS 80b Instruct
Requires ml.g5.48xlarge instance.

To have the right instance types and how to request them, read Amazon SageMaker requirements

{{% notice note %}}
Make sure to review IDEFICS models license sections.
{{% /notice %}}


To deploy a multimodal model, follow the deploy instructions and select one of the supported models (press Space to select/deselect) from the magic-config CLI step and deploy as instructed in the above section.

{{% notice note %}}
⚠️ Amazon SageMaker are billed by the hour. Be aware of not letting this model run unused to avoid unnecessary costs.
{{% /notice %}}

### Multi-Session Chat: evaluate multiple models at once
Send the same query to 2 to 4 separate models at once and see how each one responds based on its own learned history, context and access to the same powerful document retriever, so all requests can pull from the same up-to-date knowledge.

sample

### Experiment with multiple RAG options with Workspaces
A workspace is a logical namespace where you can upload files for indexing and storage in one of the vector databases. You can select the embeddings model and text-splitting configuration of your choice.

sample

### Unlock RAG potentials with Workspaces Debugging Tools
The solution comes with several debugging tools to help you debug RAG scenarios:

Run RAG queries without chatbot and analyse results, scores, etc.
Test different embeddings models directly in the UI
Test cross encoders and analyse distances from different functions between sentences.
sample

### Full-fledged User Interface
The repository includes a CDK construct to deploy a full-fledged UI built with React to interact with the deployed LLMs/MLMs as chatbots. Hosted on Amazon S3 and distributed with [Amazon CloudFront](https://aws.amazon.com/cloudfront/).

Protected with [Amazon Cognito Authentication](https://aws.amazon.com/cognito/) to help you interact and experiment with multiple LLMs/MLMs, multiple RAG engines, conversational history support and document upload/progress.

The interface layer between the UI and backend is built with [AppSync](https://cloudscape.design/) for management requests and for realtime interaction with chatbot (messages and responses) using GraphQL subscriptions.

Design system provided by [AWS Cloudscape Design System.](https://cloudscape.design/)

## Additional Resources

| Resource                           | Description                                                                                                                                   |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| [Secure Messenger GenAI Chatbot](https://github.com/aws-samples/secure-messenger-genai-chatbot) | A messenger built on Wickr that can interface with this chatbot to provide Q&A service in tightly regulated environments (i.e. HIPAA).         |
| [Project Lakechain](https://github.com/awslabs/project-lakechain)             | A powerful cloud-native, AI-powered, document (docs, images, audios, videos) processing framework built on top of the AWS CDK.                 |
| [AWS Generative AI CDK Constructs](https://github.com/awslabs/generative-ai-cdk-constructs/) | Open-source library extension of the [AWS Cloud Development Kit (AWS CDK)](https://docs.aws.amazon.com/cdk/v2/guide/home.html) aimed to help developers build generative AI solutions using pattern-based definitions for their architecture. |
| [Artifacts and Tools for Bedrock](https://github.com/aws-samples/artifacts-and-tools-for-bedrock) | An innovative chat-based user interface with support for tools and artifacts. It can create graphs and diagrams, analyze data, write articles, create web pages, generate files, and much more. |
