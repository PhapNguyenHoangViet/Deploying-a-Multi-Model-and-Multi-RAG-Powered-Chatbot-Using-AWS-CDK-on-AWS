+++
title = "Deployment"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++ 
### Deployment

1. Clone the repository.

```
git clone https://github.com/aws-samples/aws-genai-llm-chatbot
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/001-1-deployment.png?width=90pc)


2. Move into the cloned repository.

```
cd aws-genai-llm-chatbot
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/002-1-deployment.png?width=90pc)

3. Install the project dependencies and build the project.

```
npm ci && npm run build
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/003-1-deployment.png?width=90pc)

4. (Optional) Run the unit tests
- Install python3
```
sudo apt install python3-pip
```
- Run the unit tests
```
npm run test && pip install -r pytest_requirements.txt && python3 -m pytest tests
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/004-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/011-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/012-1-deployment.png?width=90pc)


5. Once done, run the configuration command to help you set up the solution with the features you need:

```
npm run config
```

You'll be prompted to configure the different aspects of the solution, such as:

- The LLMs or MLMs to enable (we support all models provided by Bedrock that [**were enabled**](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html) along with SageMaker hosted Idefics, FalconLite, Mistral and more to come).
- Setup of the RAG system: engine selection (i.e. Aurora w/ pgvector, OpenSearch, Kendra).
- Embeddings selection.
- Limit accessibility to website and backend to VPC (private chatbot).
- Add existing Amazon Kendra indices as RAG sources
When done, answer Y to create or update your configuration.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/013-1-deployment.png?width=90pc)

Your configuration is now stored under `bin/config.json`. You can re-run the `npm run config` command as needed to update your `config.json`

6. Install the AWS CDK CLI
Use the Node Package Manager to install the CDK CLI. We recommend that you install it globally using the following command:
```
npm install -g aws-cdk
```
- **Set AWS Credentials as Environment Variables:**

Replace your_aws_access_key_id and your_aws_secret_access_key with your actual AWS credentials:
```
export AWS_ACCESS_KEY_ID=your_aws_access_key_id
export AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/006-1-deployment.png?width=90pc)

These commands temporarily set your AWS credentials in the current terminal session. They are essential for authenticating AWS CLI or SDK calls within the session.

- **Verify the Environment Variables:**
You can check if the variables were set correctly using the following commands:

```
echo $AWS_ACCESS_KEY_ID
echo $AWS_SECRET_ACCESS_KEY
```

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/007-1-deployment.png?width=90pc)

This will print the values of AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY in the terminal to confirm they've been set.

7. You can now deploy by running:

```
npm run cdk deploy
```

{{% notice note %}}
This step duration can vary greatly, depending on the Constructs you are deploying.
{{% /notice %}}


![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/010-1-deployment.png?width=90pc)


You can view the progress of your CDK deployment in the [CloudFormation console](https://console.aws.amazon.com/cloudformation/home) in the selected region.


![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/008-1-deployment.png?width=90pc)


8. Once deployed, take note of the User Interface, User Pool and, if you want to interact with 3P models providers, the Secret where to store API_KEYS to access 3P model providers.

```
...
Outputs:
GenAIChatBotStack.UserInterfaceUserInterfaceDomanNameXXXXXXXX = dxxxxxxxxxxxxx.cloudfront.net
GenAIChatBotStack.AuthenticationUserPoolLinkXXXXX = https://xxxxx.console.aws.amazon.com/cognito/v2/idp/user-pools/xxxxx_XXXXX/users?region=xxxxx
GenAIChatBotStack.ApiKeysSecretNameXXXX = ApiKeysSecretName-xxxxxx
...
```

9. Open the generated **Cognito User Pool** Link from outputs above.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/009-1-deployment.png?width=90pc)

10. Add a user that will be used to log into the web interface.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/009-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/009-1-deployment.png?width=90pc)

11. Open the User **Interface Url** for the outputs above, i.e. dxxxxxxxxxxxxx.cloudfront.net.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/014-1-deployment.png?width=90pc)

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/015-1-deployment.png?width=90pc)

12. Login with the user created in Step 9 and follow the instructions.

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/016-1-deployment.png?width=90pc)

- AWS GenAI Chatbot

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/017-1-deployment.png?width=90pc)