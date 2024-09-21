+++
title = "Install Docker"
date = "r Sys.Date()"
weight = 3
chapter = false
pre = "<b>3.3. </b>"
+++

1. **Updates the package list** on your system.
```
sudo apt-get update
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/001-3-installdocker.png?width=90pc)

2. Installs **Docker**.
```
sudo apt-get install -y docker.io
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/002-3-installdocker.png?width=90pc)

3. Starts the **Docker service** and **enables Docker** to start automatically at boot.
```
sudo systemctl start docker
sudo systemctl enable docker
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/003-3-installdocker.png?width=90pc)

4. Adds your user to the Docker group to run Docker commands without sudo.
```
sudo usermod -aG docker $USER
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/004-3-installdocker.png?width=90pc)

5. Displays the installed **Docker version.**
```
docker --version
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/005-3-installdocker.png?width=90pc)

6. Updates the current group membership to apply changes.
Lists the groups your user is a member of.
Lists permissions of the Docker socket file.
```
newgrp docker
groups $USER
ls -l /var/run/docker.sock
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/006-3-installdocker.png?width=90pc)

7. Sets permissions on the Docker socket file to allow read/write for the owner and group.
Changes the owner and group of the Docker socket file.
```
sudo chmod 660 /var/run/docker.sock
sudo chown root:docker /var/run/docker.sock
```

![installdocker](/Deploying-a-Multi-Model-and-Multi-RAG-Powered-Chatbot-Using-AWS-CDK-on-AWS/images/3-setupproject/3-installdocker/007-3-installdocker.png?width=90pc)