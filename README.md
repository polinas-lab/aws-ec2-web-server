Project Journey

AWS EC2 Web Server Project

Why I Started This Project

After completing my first AWS project on Amazon S3 Static Website Hosting and my second project on AWS IAM User Management, I wanted to move beyond storage and security and explore the compute side of cloud computing.

While S3 allowed me to host a website without managing any servers, I became curious about how websites are hosted when full control over the operating system and server environment is required.

I wanted to understand:

* How cloud servers are created
* How administrators connect to them remotely
* How networking and security work
* How web servers host websites

To answer these questions, I decided to build my first web server using Amazon EC2.

---

Project Objective

The goal of this project was to:

* Understand Amazon EC2 fundamentals
* Launch a Linux server in AWS
* Configure network security
* Connect to a server using SSH
* Install and manage Apache Web Server
* Deploy a website on EC2
* Understand the difference between S3 and EC2 hosting

---

Step 1: Selecting Amazon Linux

The first step was choosing an operating system for the EC2 instance.

I selected **Amazon Linux 2023**, an AWS-optimized Linux distribution commonly used in cloud environments.

Since this was my first cloud server, I wanted to use an operating system designed specifically for AWS workloads and widely used in production environments.

Amazon Linux Selection

The screenshot below shows the Amazon Linux operating system selected during instance creation.

![Amazon Linux Selected](screenshots/amazon-linux-selected.png)

What I Learned

* EC2 instances require an operating system.
* Amazon Linux is optimized for AWS.
* Cloud servers work similarly to physical servers but are hosted in AWS data centers.

---

Step 2: Launching the EC2 Instance

After selecting the operating system, I launched my first EC2 instance.

An EC2 instance is essentially a virtual machine running in the cloud. It provides computing resources such as CPU, memory, storage, and networking.

Unlike Amazon S3, which is fully managed, EC2 gives users complete control over the operating system and software installed on the server.

EC2 Instance Running

The screenshot below shows my EC2 instance successfully launched and running.

![EC2 Running](screenshots/instance-running.png)

Why This Matters

Launching an EC2 instance is one of the most fundamental tasks in AWS because applications, APIs, databases, and websites often run on cloud servers.

---

Step 3: Configuring Network Security

Before accessing the server, I needed to configure Security Groups.

Security Groups act as virtual firewalls and determine which traffic can reach an EC2 instance.

I configured:

* Port 22 (SSH) for secure remote access
* Port 80 (HTTP) for website access

SSH access was restricted to my own IP address while HTTP traffic was allowed so visitors could access the website.

Security Group Configuration

The screenshot below shows the Security Group and networking configuration.

![Network Settings](screenshots/network_settings.png)

What I Learned

* Security Groups function as virtual firewalls.
* Network access should follow security best practices.
* Firewall rules are critical for protecting cloud resources.

---

Step 4: Connecting to the Server Using SSH

After launching the server, I connected to it remotely from my Windows machine using SSH and the PEM key pair generated during instance creation.

SSH (Secure Shell) is a secure protocol used by cloud engineers and system administrators to manage Linux servers remotely.

This was my first experience directly interacting with a Linux server hosted in the cloud.

SSH Connection Established

The screenshot below shows the successful SSH connection to the EC2 instance.

![SSH Connected](screenshots/ssh-connected.png)

Why This Matters

SSH is one of the most widely used tools in cloud computing because it allows administrators to securely manage infrastructure from anywhere.

---

Step 5: Installing Apache Web Server

Once connected to the server, I installed Apache HTTP Server.

Apache is responsible for receiving browser requests and serving website content to users.

After installation, I started the Apache service and configured it to start automatically whenever the server reboots.

### Apache Installation and Status

The screenshot below shows Apache successfully installed and running.

![Apache Running](screenshots/apache-running.png)

Commands Used

```bash
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
```

What I Learned

* Apache is a web server application.
* Services can be managed using Linux commands.
* Web servers process requests and deliver website content.

---

Step 6: Creating and Deploying the Website

With Apache running, the next step was to create a website.

I created a simple HTML page and placed it inside Apache's default web root directory:

```text
/var/www/html
```

Any file placed in this directory can be served to visitors through the web server.

This step transformed the EC2 instance from a Linux server into a functioning web server.

### HTML File Created

The screenshot below shows the HTML file being created and added to the server.

![HTML Added](screenshots/html_web_added.png)

### Website Source Code

The HTML file used in this project can be found here:

[View index.html](website/index.html)

What I Learned

* Web servers require content to serve.
* Apache automatically serves files located in its web root directory.
* Linux file management is an important part of website deployment.

---

Step 7: Accessing the Website

After configuring Apache and deploying the HTML page, I opened the EC2 instance's public IPv4 address in a browser.

The successful webpage confirmed that:

* The EC2 instance was running
* Apache was operational
* Security Group rules were configured correctly
* The website had been deployed successfully

Website Successfully Hosted on EC2

The screenshot below shows the final website running on the EC2 server.

![Website Live](screenshots/ec2-website-live.png)

---

Key Difference Between Amazon S3 and Amazon EC2

One of the most valuable lessons from this project was understanding the difference between Amazon S3 and Amazon EC2.

Amazon S3

* Fully managed service
* Static website hosting
* No operating system management
* No server administration

Amazon EC2

* Full control over the operating system
* Supports dynamic applications
* Requires server configuration
* Requires software installation and maintenance

This project gave me hands-on experience managing the infrastructure myself rather than relying entirely on AWS-managed services.

---

Project Architecture

```text
Windows Laptop
       │
       ▼
SSH Connection
       │
       ▼
Amazon EC2 Instance
       │
       ▼
Apache HTTP Server
       │
       ▼
Hosted Website
```

---

What I Learned

Through this project, I gained practical experience with:

* Amazon EC2
* Linux Administration
* SSH
* Security Groups
* Apache Web Server
* Cloud Networking
* Website Deployment
* Public IP Addressing
* Infrastructure Management

---

Project Outcome

At the end of this project, I successfully:

* Launched an EC2 instance
* Configured network security
* Connected to a Linux server using SSH
* Installed Apache Web Server
* Created and deployed a website
* Hosted the website using a public IP address

This project provided my first real experience managing cloud infrastructure directly.

---

Conclusion

While my first AWS project focused on hosting a website using Amazon S3 and CloudFront, and my second project focused on securing AWS environments using IAM, this project introduced me to the compute layer of cloud computing.

For the first time, I worked directly with a Linux server, configured networking rules, installed software, and deployed a website from scratch.

This project strengthened my understanding of cloud infrastructure and gave me practical experience with one of the most important AWS services: Amazon EC2.

It marks another significant milestone in my AWS learning journey as I continue exploring VPC, Route 53, Lambda, DynamoDB, Auto Scaling, Load Balancers, and more advanced cloud architectures.
