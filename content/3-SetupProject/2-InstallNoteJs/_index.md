+++
title = "Install NodeJs"
date = "r Sys.Date()"
weight = 2
chapter = false
pre = "<b>3.2. </b>"
+++

1. **Updates** the package list on your system.

sudo apt update

- This command updates the list of available packages and their versions on your system. It doesn’t install or upgrade any packages; it just refreshes the package index.

![installnodejs](/images/3-setupproject/2-installnodejs/001-2-installnodejs.png?width=90pc)



2. Downloads and installs **NVM** **(Node Version Manager)**.
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash

- This command downloads and runs the NVM (Node Version Manager) installation script from GitHub. curl fetches the script, and the | bash part pipes it to the bash shell for execution. NVM allows you to manage multiple versions of Node.js on your system.


![installnodejs](/images/3-setupproject/2-installnodejs/002-2-installnodejs.png?width=90pc)

3. Applies the changes made by **NVM** to your current shell session.
source ~/bashrc

- This command reloads the .bashrc file in your home directory to apply the changes made by the NVM installation script. It ensures that NVM commands are available in your current shell session.

- Checks the installed version of **NVM**.
nvm --version

   - This command checks and displays the installed version of NVM to verify that it has been installed correctly.

![installnodejs](/images/3-setupproject/2-installnodejs/003-2-installnodejs.png?width=90pc)

4. Installs **Node.js** version 18 using NVM.
nvm install 18

- Installs Node.js version 18 using NVM. You can install and manage different versions of Node.js with NVM.

![installnodejs](/images/3-setupproject/2-installnodejs/004-2-installnodejs.png?width=90pc)

5. Displays **the version of NodeJs and the version of npm**.
node -v
npm -v


![installnodejs](/images/3-setupproject/2-installnodejs/005-2-installnodejs.png?width=90pc)

6. **Updates** the package list again.
sudo apt update


![installnodejs](/images/3-setupproject/2-installnodejs/006-2-installnodejs.png?width=90pc)