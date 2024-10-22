+++
title = "Run user interface locally"
date = "`r Sys.Date()`"
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++
#### Run user interface locally

You can run this vite react app locally following these steps.


#### Option 1: Obtain environment configuration

Grab the `aws-exports.json` from the CloudFront distribution endpoint you obtained from the CDK Output, and save it into `./lib/user-interface/react-app/public/` folder. Then run `npm run dev`.

For example:

```bash
cd lib/user-interface/react-app/public
curl -O https://dxxxxxxxxxxxx.cloudfront.net/aws-exports.json
cd ..
npm run dev
```
![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/018-1-deployment.png?width=90pc)


#### Option 2: Set configuration as env variable

```bash
export AWS_PROJECT_REGION="..."
export AWS_COGNITO_REGION="..."
export AWS_USER_POOLS_ID="..."
export AWS_USER_POOLS_WEB_CLIENT_ID="..."
export API_DISTRIBUTION_DOMAIN_NAME="..."
export RAG_ENABLED=1|0
export DEFAULT_EMBEDDINGS_MODEL="..."
export DEFAULT_CROSS_ENCODER_MODEL="..."
npm run build:dev
npm run dev
```

**Login with the user created**

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/019-1-deployment.png?width=90pc)

- AWS GenAI Chatbot

![4-deployment](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/4-deploy/020-1-deployment.png?width=90pc)