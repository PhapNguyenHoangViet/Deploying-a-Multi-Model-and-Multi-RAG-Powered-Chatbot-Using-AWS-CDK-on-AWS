+++
title = "Setup Security Groups"
date = "`r Sys.Date()`"
weight = 3
chapter = false
pre = "<b>2.3. </b>"
+++

Next, we need to secure the EC2 instances.
- In the `Security` section of the [VPC console](https://us-east-1.console.aws.amazon.com/vpcconsole/home?region=us-east-1#Home:)
- Select Security groups
- Click Create security group

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/001-3-setupsecuritygroups.png?width=90pc)

We will enter the following settings for the security group of the EC2 instance:
- Name: `chatbot-ec2-sg`
- Description: `Allow SSH and other private connections`
- VPC: select `chatbot-vpc`

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/002-3-setupsecuritygroups.png?width=90pc)

- In Inbound Rules, add a rule:
  - Type: **SSH**
  - Source: **My IP**

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/003-3-setupsecuritygroups.png?width=90pc)

- Created **security groups**

![creatingvpc](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/2-preparation-steps/3-setupsecuritygroups/004-3-setupsecuritygroups.png?width=90pc)

