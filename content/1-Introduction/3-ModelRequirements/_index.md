+++
title = "Model Requirements"
date = 2024
weight = 3
chapter = false
pre = "<b>1.3. </b>"
+++

### **Amazon SageMaker requirements (for self-hosted models only)[](https://aws-samples.github.io/aws-genai-llm-chatbot/documentation/model-requirements.html#amazon-sagemaker-requirements-for-self-hosted-models-only)**

**Instance type quota increase**

If you are looking to self-host models on Amazon SageMaker, you'll likely need to request an increase in service quota for specific SageMaker instance types, such as the `ml.g5` instance type. This will give access to the latest generation of GPU/Multi-GPU instance types. [You can do this from the AWS console](https://console.aws.amazon.com/servicequotas/home/services/sagemaker/quotas)

### **Amazon Bedrock requirements[](https://aws-samples.github.io/aws-genai-llm-chatbot/documentation/model-requirements.html#amazon-bedrock-requirements)**

**Base Models Access**

If you are looking to interact with models from Amazon Bedrock, you need to [request access to the base models in one of the regions where Amazon Bedrock is available](https://console.aws.amazon.com/bedrock/home?#/modelaccess). Make sure to read and accept models' end-user license agreements or EULA.

{{% notice note %}}
You can deploy the solution to a different region from where you requested Base Model access.
**While the Base Model access approval is instant, it might take several minutes to get access and see the list of models in the UI.**
{{% /notice %}}


- Find **Bedrock**
- Click **Bedrock**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/001-3-modelrequirements.png?width=90pc)


- Click **Model access**
- Click **Enable all models**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/002-3-modelrequirements.png?width=90pc)

- Click **next**
![3-modelrequirements](/images/1-introduction/3-modelrequirements/003-3-modelrequirements.png?width=90pc)

- Click **Submit**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/004-3-modelrequirements.png?width=90pc)

- **Amazon bedrock**

![3-modelrequirements](/images/1-introduction/3-modelrequirements/005-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/images/1-introduction/3-modelrequirements/006-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/images/1-introduction/3-modelrequirements/007-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/images/1-introduction/3-modelrequirements/008-3-modelrequirements.png?width=90pc)
