+++
title = "Creating IAM User"
date = "`r Sys.Date()`"
weight = 1
chapter = false
pre = "<b>2.1. </b>"
+++

### Create IAM User

1. Log in to [IAM console](https://console.aws.amazon.com/iam/home#/home)

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/001-1-creatingiamuser.png?width=90pc)

2. In the left navigation bar, select User, then click Add User

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/002-1-creatingiamuser.png?width=90pc)

3. On the **Set user details** page, enter the following information:
    - User name: **Chatbot-user**
    - Access type: tick **AWS Management Console access** to allow users to access AWS Management Console
    - Console password: select **Custom password** and enter the password you like for the user
    - Require password reset: uncheck this option so that the user does not need to change the password when logging in for the first time
    - Check and select **Next: Permissions**

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/003-1-creatingiamuser.png?width=90pc)
![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/004-1-creatingiamuser.png?width=90pc)

4. On the **Set permissions** page, we operate:
- Select **Attach existing policies directly** to choose the method of assigning permissions directly to the user.

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/005-1-creatingiamuser.png?width=90pc)

- An IAM User with AdministratorAccess policy granted (for production, we recommend restricting access as needed)

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/006-1-creatingiamuser.png?width=90pc)

5. On the Add tags (optional) page, keep the defaults and select Next: Review

6. On the Review page, check the information and select Create user

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/007-1-creatingiamuser.png?width=90pc)

7. When the initialization is complete, press **Close** to return to the **IAM Console**.

8. Enabled with **MFA**

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/008-1-creatingiamuser.png?width=90pc)

- Enabled with MFA
- Create access key

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/009-1-creatingiamuser.png?width=90pc)

9. Create **access key**

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/011-1-creatingiamuser.png?width=90pc)

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/012-1-creatingiamuser.png?width=90pc)

   - Download .csv file
   - Done

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/013-1-creatingiamuser.png?width=90pc)

10. Created **IAM User**

![creatingiamuser](/images/2-preparation-steps/1-creatingiamuser/014-1-creatingiamuser.png?width=90pc)