+++
title = "Launch EC2 instance"
date = "`r Sys.Date()`"
weight = 4
chapter = false
pre = "<b>2.4. </b>"
+++

### Launch EC2 instance

1. Go to [AWS Management Console](https://aws.amazon.com/console/)

    - Find **EC2**
    - Select **EC2**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/001-4-launchec2instance.png?width=90pc)

2. In the **EC2** interface

    - Select **Instances**
    - Select **Launch instances**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/002-4-launchec2instance.png?width=90pc)

3. Name instance, enter `Chatbot-ec2`

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/003-4-launchec2instance.png?width=90pc)

4. Made for **AMI**

    - Select **Quick Start**
    - Select **Ubuntu**
    - Amazon Machine Image (AMI): Ubuntu Server 22.04 LTS (HVM), SSD Volume Type
    - Architecture: 64-bit (x86)

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/004-4-launchec2instance.png?width=90pc)

5. Select **Instance type**

    - Select **m5.large** or larger as Instance Type.
    
![launchec2instance](/images/2-preparation-steps/4-launchec2instance/005-4-launchec2instance.png?width=90pc)

- Select **Create new key pair**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/006-4-launchec2instance.png?width=90pc)

6. Configure **key pair**.

    - Key pair name: `chatbot-keypair`
    - Key pair type: **RSA**
    - Private key file format: **.pem**
    - **Create key pair**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/007-4-launchec2instance.png?width=90pc)

7. Configure **Network**

   - **VPC**, select the created VPC.
   - **Subnet**, select **Public subnet**
   - Check if **Auto-assign public IP**?. If you have not reviewed the step of allocating public IP in the step of creating VPC.
   - Select Select existing security group and then select `chatbot-ec2-sg`

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/008-4-launchec2instance.png?width=90pc)

8. Configure **storage**
    
    - **100 GiB**

![launchec2instance](/images/2-preparation-steps/4-launchec2instance/009-4-launchec2instance.png?width=90pc)

9.  Select **Launch instance**

10.  Successfully initialized instance and select **View all instances**