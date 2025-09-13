# 🌐 AWS Project 1: Web Server on Amazon EC2

## 📌 Project Overview
A beginner-friendly project where I deployed an Apache web server on an Amazon EC2 instance.  
The goal was to learn the basics of launching an EC2 instance, configuring security groups, and hosting a simple website.

---

## 🛠️ AWS Services Used
- **Amazon EC2** – for hosting the web server  
- **Security Groups** – for controlling inbound/outbound traffic  
- **Elastic IP** – to assign a static IP address for the server  

---

## 🏗️ Architecture Diagram
![Architecture Diagram](https://github.com/rohaanfarrukh/AWS-projects/blob/main/aws_projecct1/project_1/project1_diagram.png)


---

## 🚀 Steps I Took
1. Created a new EC2 instance (t2.micro, Amazon Linux 2 – Free Tier).
2. Configured security group rules to allow:
   - **Port 22 (SSH)** for remote access
   - **Port 80 (HTTP)** for web traffic
3. Connected to the instance via SSH.
4. Installed Apache (`sudo yum install httpd -y`) and started the service.
5. Placed a sample `index.html` file in `/var/www/html`.
6. Allocated and attached an Elastic IP to keep the server accessible.

---

## 🧠 Lessons Learned
- How to safely SSH into an EC2 instance.
- Why security group rules are important for controlling access.
- How to host a simple website on a cloud server.

---

## 📸 Screenshots
| Step | Screenshot |
|------|-------------|
| EC2 instance running | ![EC2 Screenshot](https://github.com/rohaanfarrukh/AWS-projects/blob/main/aws_projecct1/project_1/website.png) |
| Webpage in browser | ![Webpage Screenshot](https://github.com/rohaanfarrukh/AWS-projects/blob/main/aws_projecct1/project_1/ec2%20instances.png) |

![EC2 Screenshot](https://github.com/rohaanfarrukh/AWS-projects/blob/main/aws_projecct1/project_1/website.png) 
---

## 📢 Key Takeaways
This project gave me hands-on experience with EC2, basic networking, and server setup in AWS.  
It’s a strong starting point for building more complex cloud architectures.

---

