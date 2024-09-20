+++
title = "Connecting to EC2 Instance from VSCode"
date = "`r Sys.Date()`"
weight = 5
chapter = false
pre = "<b>2.5. </b>"
+++

Connecting via SSH from Visual Studio Code to an EC2 Instance is a quick alternative to using Cloud9.

### Download Visual Studio Code and the Remote - SSH extension
You can download VS Code here: [Download VSCode](https://code.visualstudio.com/download)

Once downloaded, install the Remote - SSH extension.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/001-5-connecttoec2fromvscode.png?width=90pc)

- Click on **Connect to Host.**


![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/002-5-connecttoec2fromvscode.png?width=90pc)

- Click on **Add New SSH Host.**

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/003-5-connecttoec2fromvscode.png?width=90pc)

- In the input box, enter `chatbot-ec2` and press Enter.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/004-5-connecttoec2fromvscode.png?width=90pc)

- Click the link in C:\Users\vietp.ssh\config to configure.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/005-5-connecttoec2fromvscode.png?width=90pc)

- Click on **Open Config**.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/006-5-connecttoec2fromvscode.png?width=90pc)

- In the SSH configuration block, replace the placeholder with the correct IPv4 address of the EC2 Instance and the path to your Key Pair on your machine.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/007-5-connecttoec2fromvscode.png?width=90pc)

- Click on **Connect to Host.**

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/008-5-connecttoec2fromvscode.png?width=90pc)

- Click the SSH icon in the bottom left corner to start the Connect process.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/009-5-connecttoec2fromvscode.png?width=90pc)

- Click on Linux and wait a moment for the VSCode Server to be installed on the EC2 Instance

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/0010-5-connecttoec2fromvscode.png?width=90pc)

- Select Open Folder and click OK.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/0011-5-connecttoec2fromvscode.png?width=90pc)

- This is the interface after connecting.

![ConnectToEC2fromVSCode](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/5-connecttoec2fromvscode/0012-5-connecttoec2fromvscode.png?width=90pc)
