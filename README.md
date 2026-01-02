AWS Web Server Deployment Project
This repository documents the step-by-step process of deploying a live web server on AWS using an EC2 instance. 

🚀 Project Overview
The goal of this project was to provision a virtual Linux server, configure security protocols, install the Apache web server, and host a custom HTML project accessible via the public internet. 

🛠 Tech Stack

Cloud Provider: Amazon Web Services (AWS) 


Operating System: Ubuntu 24.04 LTS (GNU/Linux 6.14.0-1015-aws x86_64) 


Web Server: Apache/2.4.58 (Ubuntu) 


Virtual Server Type: t3.micro (Free tier eligible) 


Terminal: Windows PowerShell 

📋 Documentation of Steps
1. EC2 Instance Provisioning

Instance Name: My-first-web-server 


AMI: Canonical, Ubuntu, 24.04, amd64 


Region: Asia Pacific (Mumbai) / ap-south-1b 


Key Pair: Generated myserver-key.pem for secure authentication 

2. Network Security Configuration
To allow external traffic to reach the server, the following Inbound Rules were configured in the Security Group (launch-wizard-1): 


Port 22 (SSH): For remote command-line access 


Port 80 (HTTP): To allow standard web browsing traffic 


Port 443 (HTTPS): To support secure web endpoints 

NOTE:- Critical Configuration: To ensure the web server was accessible to the public, I manually updated the EC2 Security Group's inbound rules. I added a rule to allow traffic on Port 80 (HTTP) from any source (0.0.0.0/0), resolving initial connectivity issues.

3. Remote Server Connection
The server was accessed via SSH from a local Windows environment: 

Located the private key in the Downloads directory 

Verified SSH availability in PowerShell 

Connected using the command:


ssh -i "myserver-key.pem" ubuntu@ec2-15-206-127-34.ap-south-1.compute.amazonaws.com 

4. Environment Setup & Web Server Installation
Once logged in, the system was updated and the web server software was installed: 

Updated package lists using sudo apt update 

Upgraded existing packages using sudo apt upgrade 

Installed the Apache2 package with sudo apt install apache2 

Confirmed the Public IP Address (15.206.127.34) via curl ifconfig.me 

5. Deployment of HTML Content
A project file named myproject.html was created and hosted on the server. The file includes a personal introduction and a summary of the deployment tech stack. 

✅ Final Result
The project is successfully deployed and reachable at:


http://15.206.127.34/myproject.html 

Key Features:

Full remote server management via SSH 

Active Apache2 service running on Port 80 

Publicly accessible web content
