+++
title = "Model Requirements"
date = 2024
weight = 3
chapter = false
pre = "<b>1.3. </b>"
+++

#### Amazon SageMaker requirements (for self-hosted models only)[](https://aws-samples.github.io/aws-genai-llm-chatbot/documentation/model-requirements.html#amazon-sagemaker-requirements-for-self-hosted-models-only)

**Instance type quota increase**

If you are looking to self-host models on Amazon SageMaker, you'll likely need to request an increase in service quota for specific SageMaker instance types, such as the `ml.g5` instance type. This will give access to the latest generation of GPU/Multi-GPU instance types. [You can do this from the AWS console](https://console.aws.amazon.com/servicequotas/home/services/sagemaker/quotas)

#### Amazon Bedrock requirements[](https://aws-samples.github.io/aws-genai-llm-chatbot/documentation/model-requirements.html#amazon-bedrock-requirements)

**Base Models Access**

If you are looking to interact with models from Amazon Bedrock, you need to [request access to the base models in one of the regions where Amazon Bedrock is available](https://console.aws.amazon.com/bedrock/home?#/modelaccess). Make sure to read and accept models' end-user license agreements or EULA.

{{% notice note %}}
You can deploy the solution to a different region from where you requested Base Model access.
**While the Base Model access approval is instant, it might take several minutes to get access and see the list of models in the UI.**
{{% /notice %}}


- Find **Bedrock**
- Click **Bedrock**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/001-3-modelrequirements.png?width=90pc)


- Click **Model access**
- Click **Enable all models**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/002-3-modelrequirements.png?width=90pc)

- Click **next**
![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/003-3-modelrequirements.png?width=90pc)

- Click **Submit**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/004-3-modelrequirements.png?width=90pc)

- **Amazon bedrock**

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/005-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/006-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/007-3-modelrequirements.png?width=90pc)

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/008-3-modelrequirements.png?width=90pc)

#### HuggingFace Authentication

Some models hosted on HuggingFace require an API key for access, for example MistralAI and Meta models have now changed to be gated behind accepting their EULA

If you wish to continue using these models or access other models on HuggingFace which require authentication you can now supply this HF token as part of the installer.

When enabling sagemaker models in the installer it will now ask you for a Secrets Manager Secret ARN containing the HF API token.

You can read more about setting up access tokens on the [HF website](https://huggingface.co/docs/hub/en/security-tokens) Once you've got a token you may need to also navigate to a models page such as mistral7B to accept their terms before you can then use your token to access the model.

The secret you would create in secrets manager would be a plain text secret containing just the HF token itself.

1. Sign Up or Log In to HuggingFace
- Visit [HuggingFace](https://huggingface.co/).
- If you don’t have an account, click **Sign Up**. If you already have an account, click **Login** and enter your credentials to **Log In**.

2. Obtain API Access Tokens from HuggingFace
- After logging in, go to your **Profile** by clicking on your avatar in the top-right corner, then select **Settings**.
- On the left-hand menu, select **Access Tokens**.
- Here, you’ll see a button labeled **New Token**. Click this to create a new API access token.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/009-3-modelrequirements.png?width=90pc)

   - Name your access token and set the access level to **Read**, then click **Generate**.
   - Copy the API access token, as you will need it in the next steps.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/010-3-modelrequirements.png?width=90pc)

3. Accept Model Usage Terms (if required)
- To access restricted models like **mistral7B** or Meta models, you need to accept the model’s **EULA**.
- Go to the model page you want to use (e.g., mistral7B).
- Scroll down to the **Model Card**, and if the model requires it, you will see a button to accept the terms and conditions.
- Click **Accept** to agree to the terms and allow your access token to access the model.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/011-3-modelrequirements.png?width=90pc)

4. Create an API Secret in AWS Secrets Manager
- Go to **AWS Secrets Manager** in the AWS Management Console.
- Click **Store a new secret**.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/012-3-modelrequirements.png?width=90pc)

- Choose **Other type of secrets** and enter your HuggingFace access token.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/013-3-modelrequirements.png?width=90pc)
![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/014-3-modelrequirements.png?width=90pc)

- Name the secret, for example, **HuggingFace-Token**, and store it.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/015-3-modelrequirements.png?width=90pc)

- Save the **Secret ARN** from Secrets Manager, as you will use this ARN to provide the access token to **Amazon SageMaker**.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/016-3-modelrequirements.png?width=90pc)


#### Third-party models requirements

You can also interact with external providers via their API, such as AI21 Labs, Cohere, OpenAI, etc.

The provider must be supported in the [Model Interface](https://github.com/aws-samples/aws-genai-llm-chatbot/blob/main/lib/model-interfaces/langchain/functions/request-handler/index.py), [see available langchain integrations](https://python.langchain.com/docs/integrations/llms/) for a comprehensive list of providers.

**Example:**
1. OpenAI
- Go to the [OpenAI website](https://platform.openai.com/signup) and sign up for an account (or log in if you already have one).
- After logging in, navigate to the API keys page in your dashboard.
- Click the Create API Key button.
- Copy the API Key you just generated and store it securely.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/017-3-modelrequirements.png?width=90pc)

2. AI21 Labs
- Go to the [AI21 Labs website](https://studio.ai21.com/v2) and sign up for an account.
- Log in to your account.
- Navigate to the API keys page in your dashboard.
- Click the Generate API Key button to create a new key.
- Copy the API Key and save it securely.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/018-3-modelrequirements.png?width=90pc)

3. Cohere
- Go to the [Cohere website](https://dashboard.cohere.com/) and sign up for an account.
- Log in to your dashboard.
- Go to the API keys section in your dashboard.
- Click the Create API Key button.
- Copy the API Key and store it securely.

![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/019-3-modelrequirements.png?width=90pc)

Usually, an `API_KEY` is required to integrate with 3P models. To do so, the [Model Interface](https://github.com/aws-samples/aws-genai-llm-chatbot/blob/main/lib/model-interfaces/langchain/index.ts) deployes a Secrets in [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/), intially with an empty JSON `{}`, where you can add your API KEYS for one or more providers.

These keys will be injected at runtime into the Lambda function Environment Variables; they won't be visible in the AWS Lambda Console.

For example, if you wish to be able to interact with AI21 Labs., OpenAI's and Cohere endpoints:

- Open the [Model Interface Keys Secret](https://github.com/aws-samples/aws-genai-llm-chatbot/blob/main/lib/model-interfaces/langchain/index.ts#L38) in Secrets Manager. You can find the secret name in the stack output, too.
- Update the Secrets by adding a key to the JSON

```json
{
  "AI21_API_KEY": "xxxxx",
  "OPENAI_API_KEY": "sk-xxxxxxxxxxxxxxx",
  "COHERE_API_KEY": "xxxxx"
}
```
![3-modelrequirements](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/1-introduction/3-modelrequirements/020-3-modelrequirements.png?width=90pc)



{{% notice note %}}
In case of no keys needs, the secret value must be an empty JSON `{}`, NOT an empty string `''`.
{{% /notice %}}

Make sure that the environment variable matches what is expected by the framework in use, like Langchain ([see available langchain integrations](https://python.langchain.com/docs/integrations/llms/)).

#### Azure OpenAI integration as third party model

- Open the SharedApiKeysSecretxyz in SecretManager
- Update the Secrets by adding following keys to the JSON (or Key/values): 

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
Here we are integrating 2 other models: Model1 and Model2. 
For each one, we need to define following infos you will retrieve from your Azure OpenAI tenant. ${ModelIdentifier} is either Model1 and Model2 :
 * `AZURE_OPENAI_API_TYPE__${ModelIdentifier}`
 * `AZURE_OPENAI_API_VERSION__${ModelIdentifier}`
 * `AZURE_OPENAI_API_BASE__${ModelIdentifier}`
 * `AZURE_OPENAI_API_KEY__${ModelIdentifier}`
 * `AZURE_OPENAI_API_DEPLOYMENT_NAME__${ModelIdentifier}`