
# 🚀 How to Run a Static Website Using AWS EC2 (Apache Web Server)

This guide helps you deploy a static website using an AWS EC2 Linux instance with Apache (`httpd`).

---

## ✅ Prerequisites

- AWS account
- GitHub repository containing your static website
- Basic knowledge of Linux commands

---

## 🧩 Step-by-Step Instructions

### 🔹 Step 1: Launch EC2 Instance (Amazon Linux)

- Choose Amazon Linux 2 (or a similar Linux-based AMI)
- Configure instance details and security group to allow **HTTP (port 80)** and **SSH (port 22)**

---

### 🔹 Step 2: Connect to EC2 via SSH

Use your `.pem` key and connect via terminal:

```bash
ssh -i your-key.pem ec2-user@your-ec2-public-ip
```

---

### 🔹 Step 3: Update the EC2 Instance

```bash
sudo yum update -y
```

---

### 🔹 Step 4: Install Git

```bash
sudo yum install git -y
```

---

### 🔹 Step 5: Clone the Git Repository

```bash
git clone https://github.com/I-am-nk/AWSDemo.git
cd AWSDemo
```

---

### 🔹 Step 6: Install Apache Web Server (httpd)

```bash
sudo yum install httpd -y
```

---

### 🔹 Step 7: Copy Website Files to Apache Web Directory

Apache serves files from `/var/www/html`. Use the following commands to copy your website files:

```bash
sudo cp index.html /var/www/html/
sudo cp -r assets /var/www/html/
sudo cp -r error /var/www/html/
sudo cp -r images /var/www/html/
```

---

### 🔹 Step 8: Start the Apache Web Server

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

---

### 🔹 Step 9: Check Apache Status (Optional)

```bash
sudo systemctl status httpd
```

---

### 🔹 Step 10: Access Your Website in Browser

Open your EC2 public IP in the browser:

```
http://<your-ec2-public-ip>
```

Example:
```
http://3.141.46.108
```

---

## 🎉 Done!

You’ve successfully deployed a static website on AWS EC2 using Apache Web Server.
