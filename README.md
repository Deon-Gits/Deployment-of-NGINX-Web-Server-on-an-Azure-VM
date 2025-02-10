# Deployment-of-NGINX-Web-Server-on-an-Azure-VM
Deployment of NGINX Web Server on an Azure VM
The objective of this task is outlined below:
NGINX Installation and Configuration
• Install the NGINX web server and ensure it is running.
• Configure NGINX to serve a custom HTML page as the default page (/var/www/html/index.html) with the message:
“Welcome to DevOps Stage 0 — [Your Name]/[SlackName]”
(Replace [Your Name] with the name and [SlackName] with your Slack Username).

Steps Involved
Deploying Virtual Machine and Configuring Inbound Security Rule
The first step was to set up a newly created Virtual Machine on Azure with Ubuntu 24.04 as the image. I have greyed out my Public IP and Subscription ID.
![image](https://github.com/user-attachments/assets/2a0a433e-04ef-4008-97e9-1ffe3fe28a7b)


To access the virtual machine over the internet, an inbound security rule for SSH which utilizes port 22 had to be created in the networking tab of the Virtual Machine. With Port 22 open, this enables us to access the VM over the internet using the Public IP.


Subsequently, I used a terminal to access the Virtual machine by running the command ssh username@PublicIP. For example if user Daniel is trying to access the VM with Public IP 172.168.133.24, the command is shown as ssh Daniel@172.168.133.24

There are multiple terminals today that can be used example Putty, MobaXTerm and PS. I settled for the terminal in the Microsoft Visual Studio Code.


2. Updating the Virtual Machine
The next step would be to update the Virtual Machine using the ‘apt update’ command. I am already signed in as root so no need for Sudo in the commands.


3. Installing NGINX
Now we install NGINX using the command apt install nginx -y

