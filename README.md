# Deployment-of-NGINX-Web-Server-on-an-Azure-VM
Deployment of NGINX Web Server on an Azure VM
The objective of this task is outlined below:
NGINX Installation and Configuration
• Install the NGINX web server and ensure it is running.
• Configure NGINX to serve a custom HTML page as the default page (/var/www/html/index.html) with the message:
“Welcome to DevOps Stage 0 — [Your Name]/[SlackName]”
(Replace [Your Name] with the name and [SlackName] with your Slack Username).

Steps Involved
1. **Deploying Virtual Machine and Configuring Inbound Security Rule**
The first step was to set up a newly created Virtual Machine on Azure with Ubuntu 24.04 as the image. I have greyed out my Public IP and Subscription ID.

![image](https://github.com/user-attachments/assets/2a0a433e-04ef-4008-97e9-1ffe3fe28a7b)


To access the virtual machine over the internet, an inbound security rule for SSH which utilizes port 22 had to be created in the networking tab of the Virtual Machine. With Port 22 open, this enables us to access the VM over the internet using the Public IP.

![image](https://github.com/user-attachments/assets/646d7676-cc8c-4338-96f6-cae2a9482025)

Subsequently, I used a terminal to access the Virtual machine by running the command ssh username@PublicIP. For example if user Daniel is trying to access the VM with Public IP 172.168.133.24, the command is shown as ssh Daniel@172.168.133.24

There are multiple terminals today that can be used example Putty, MobaXTerm and PS. I settled for the terminal in the Microsoft Visual Studio Code.

![image](https://github.com/user-attachments/assets/e7ad7783-0d7b-4cab-815c-2b811e3b792b)

2. **Updating the Virtual Machine**
The next step would be to update the Virtual Machine using the ‘apt update’ command. I am already signed in as root so no need for Sudo in the commands.

![image](https://github.com/user-attachments/assets/79d25012-cd8e-4f8e-99f7-122c92e04e3c)

3. **Installing NGINX**
Now we install NGINX using the command apt install nginx -y

![image](https://github.com/user-attachments/assets/88ee2857-bb69-490c-8655-21ef5ab92729)

Subsequently, I confirmed the status of the newly installed NGINX web server by running systemctl status nginx

![image](https://github.com/user-attachments/assets/9c845de9-48f3-4346-acff-2d07c18418fe)

I would also need to add port 80 and 443 for HTTP and HTTPs connection in the networking security group of the virtual machine to enable the aformentioned protocol traffic.

![image](https://github.com/user-attachments/assets/c7c02216-c483-4957-92c1-a2605e63c0b5)

Further confirmation of this was done by placing the public IP of the virtual machine on a browser.

![image](https://github.com/user-attachments/assets/5069c912-df3d-4907-a46a-e87b02195c56)

4. **Web Page Configuration**
The next step involves configuring the web page. Firstly, confirm the existence of the index file in the html directory, this can be done by navigating through the directories using cd /var/www/html

Running a List command show us the existence of the file which I will be working on.

![image](https://github.com/user-attachments/assets/da13557a-161b-4af5-9ba3-df23354e02db)

I used the mv command to rename the file to Index.html

![image](https://github.com/user-attachments/assets/4344ecb5-90e8-4b11-b991-b3e62ffa9da1)

After this, I proceeded to edit the Index.html file with some other parameters.

![image](https://github.com/user-attachments/assets/b0624948-aaa3-49a6-9e94-73d924427ccd)

Here’s what my index page looks like after the modification of the Index.html file via vim.

![image](https://github.com/user-attachments/assets/5a01e6a8-ec53-4bc3-b2d0-38a64bd6db29)



