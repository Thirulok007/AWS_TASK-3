# 🚀 AWS Task-3: S3 + EC2 + Load Balancer Setup

## 📌 Project Overview
This project demonstrates AWS cloud services integration using:
- Amazon S3
- Amazon EC2 (2 instances)
- Application Load Balancer (ALB)
- Apache Web Server

---

## 🏗️ Architecture

- S3 bucket created for file storage and logging
- Two EC2 instances launched (Ubuntu)
- Apache installed on both servers
- Application Load Balancer used to distribute traffic between servers

---

## ☁️ 1. S3 Bucket Setup

### Steps:
- Created S3 bucket with **private access (no public access)**
- Uploaded sample file (`a.txt`)
- Enabled logging using AWS CloudWatch

### Result:
- File successfully stored in S3
- Logs monitored via CloudWatch log groups

---

## 🖥️ 2. EC2 Instances Setup

### Instances Created:
- web-server-1 → 3.110.46.49
- web-server-2 → 3.110.147.135

### Configuration:
- AMI: Ubuntu Server
- Instance Type: t3.micro
- Security Group:
  - SSH (22)
  - HTTP (80)

---

## 🌐 3. Apache Web Server Setup

### Installed on both EC2 instances:

```bash
sudo apt update
sudo apt install apache2 -y
Web Pages:

Server 1:

echo "<h1>Server 1 Working</h1>" | sudo tee /var/www/html/index.html

Server 2:

echo "<h1>Server 2 Working</h1>" | sudo tee /var/www/html/index.html
⚖️ 4. Application Load Balancer (ALB)
Setup:
Created Application Load Balancer (Internet-facing)
Created Target Group (HTTP:80)
Registered both EC2 instances
DNS:
http://web-alb-92646548.ap-south-1.elb.amazonaws.com
🔁 Load Balancing Result

When accessing ALB DNS:

Refresh shows Server 1 response
Next refresh shows Server 2 response

✔ Confirms load balancing is working successfully
📊 Final Result

✔ S3 bucket created and tested
✔ EC2 instances deployed
✔ Apache web server configured
✔ Application Load Balancer working
✔ Traffic distributed between servers

🎯 Conclusion

Successfully implemented a basic AWS cloud architecture with storage, compute, and load balancing services.
