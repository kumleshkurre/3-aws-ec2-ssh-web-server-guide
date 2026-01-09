# 🖥️ Accessing & Managing AWS EC2 Instance (SSH Guide)

This guide explains how to SSH into an EC2 instance, edit web server files, connect from Windows using PuTTY, and terminate an EC2 instance safely.

## 🔐 What is SSH?

SSH (Secure Shell) allows you to securely control and access a remote machine (EC2 instance) using a terminal 🧑‍💻.

## 🐧 SSH into EC2 Instance (Linux / EC2 Browser Connect)
- 🔹 Steps:
- 🌐 Go to AWS Management Console
- 📂 Open EC2 Dashboard
- 🖥️ Select your EC2 Instance
- 🔗 Click Connect
- Choose EC2 Instance Connect
- Click Connect again
➝ Linux terminal will open in browser

- 📁 Navigate to Web Server Directory
``` cd /var/www/html
 ls
```
- ✏️ Edit index.html File
```
sudo vi index.html
```
- 📝 In vi editor:
- Press i → Edit mode
- Make changes
- Press Esc
- Type :wq → Save & exit
 
- 📄 Verify File Content
```
cat index.html
```

- ✅ Changes successfully applied to web page

---
## 🪟 SSH into EC2 from Windows (PuTTY)
- 🔹 Requirements:
- 🖥️ PuTTY
- 🔑 PuTTYgen
- .pem key file (mywebserver-key.pem)
---
## 🔹 Convert PEM to PPK
- Open PuTTYgen
- Click Load
- Select mywebserver-key.pem
- Click Save private key
- File saved as mywebserver-key.ppk 🔐

  ## 🔹 Connect Using PuTTY

- Open PuTTY
- In Host Name field, enter:
- ec2-user@<Public-IP-Address> (Public IP of EC2 instance)
- Go to:
- SSH → Auth → Credentials
- Click Browse
- Select mywebserver-key.ppk
- Saved Session:
- type Session name mywebserver
- click save and Click Open
- 🔹 Login
- When terminal is opens and enter: username: ec2-user
- ✅ You are now connected to EC2 instance 🎉
---
## 🛑 How to Terminate EC2 Instance

- ⚠️ Warning: Termination will permanently delete the instance.
- 🔹 Steps:
- 📂 Go to EC2 Dashboard
- 🖥️ Select the EC2 Instance
- Click Instance state
- Select Terminate instance
- Confirm Terminate
- 🗑️ Instance successfully deleted

## ⚡ Best Practices

- 🔑 Always keep your key pair safe
- 🚫 “Do not share .pem or .ppk files with anyone, as they provide SSH access.”
- 🧹 Terminate unused instances to avoid extra AWS charges
- 🔐 Use Security Groups carefully
---

## 🎯 Purpose of This Guide

- Understand SSH access to EC2
- Learn Linux file editing
- Connect EC2 from Windows & Linux
- Practice basic EC2 lifecycle management
---
## 👨‍💻 Author

Kumlesh Kurre
💼 IT Support & Network Engineer

⭐ If you find this guide helpful, don’t forget to star ⭐ the GitHub repository
