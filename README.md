# AWS Static Web Hosting on EC2

This project demonstrates how to deploy and host a static website on an **AWS EC2 instance** using the **Apache Web Server**. It covers IAM security best practices, Linux terminal commands, and network security configuration.

## 🏗️ Architecture Summary
* **Cloud Provider:** AWS
* **Region:** Asia Pacific (Mumbai) `ap-south-1`
* **Instance Type:** t3.micro (Free Tier eligible)
* **Operating System:** Amazon Linux 2023
* **Web Server:** Apache (httpd)

## 🛠️ Implementation Steps

### 1. Security & IAM Setup
* Created a dedicated IAM user `AWSAdmin` with `AdministratorAccess`.
* Avoided using the Root account for daily tasks following AWS security best practices.

### 2. Infrastructure & Networking
* Launched an EC2 instance in the Mumbai region.
* Configured **Security Groups** to allow inbound traffic on:
  * **Port 22 (SSH):** For remote terminal access.
  * **Port 80 (HTTP):** To make the website accessible to the public.

### 3. Server Configuration (Linux Terminal)
Connected to the instance via SSH and executed the following commands:
```bash
sudo su
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
