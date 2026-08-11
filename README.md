# My First Website on AWS EC2

A simple project demonstrating how to launch an Amazon EC2 instance, connect to it, install Apache (httpd), and serve a basic static webpage — all from the AWS Free Tier.

## Overview

- **Instance ID:** i-0ce39a1b3630f29fc (named "Fictic")
- **Region:** Asia Pacific (Mumbai) — ap-south-1
- **OS:** Amazon Linux 2023
- **Web Server:** Apache (httpd)
- **Access:** EC2 Instance Connect (browser-based SSH)

## Steps

### 1. Launch the EC2 Instance
Launched a new EC2 instance from the AWS Console. The success banner confirms the instance was created.

![Launch Success](images/01-launch-success.jpg)

### 2. View Instance in the EC2 Dashboard
Checked the EC2 dashboard to confirm the instance is running, along with associated resources (key pair, security groups) and available free-tier credits.

![EC2 Dashboard](images/02-ec2-dashboard.jpg)

### 3. Connect to the Instance & Update the System
Connected to the instance using EC2 Instance Connect, then updated all packages:

```bash
sudo yum update -y
```

![Connect and Update](images/03-connect-update.png)

### 4. Install Apache and Create the Webpage
Installed the Apache web server, started and enabled the service, then created a simple HTML page:

```bash
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo su
echo "<h1>My First Website on AWS!</h1>" > /var/www/html/index.html
```

![Install Apache](images/04-install-httpd.jpg)

### 5. View the Live Website
Visited the instance's public IP address in the browser to confirm the site is live.

![Live Website](images/05-live-website.png)

## Key Takeaways

- How to launch and configure a free-tier EC2 instance on AWS
- How to connect to an instance via EC2 Instance Connect
- How to install and configure Apache (httpd) on Amazon Linux 2023
- How to serve a basic static HTML page over HTTP

## Tech Stack

- AWS EC2
- Amazon Linux 2023
- Apache HTTP Server (httpd)
