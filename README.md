# Linux Server Setup (Learning Project)
This is a small project I did while learning Linux and DevOps.
In this project I created a Linux server on AWS and installed a web server called Nginx. I also learned how to check if services are running in Linux.

## Goal: Understand how a Linux server works and deploy a simple web server using Nginx.

---

## Step 1: Connect to the server
First I created an EC2 Linux server on AWS and connected to it using SSH.
Command used:
ssh ec2-user@server-ip
SSH means Secure Shell.  
It allows us to connect to a remote Linux machine.

---

## Step 2: Update the system
Before installing anything, I updated the server.
Command:
sudo dnf update
sudo allows us to run commands as an administrator.

---

## Step 3: Install Nginx
Nginx is a web server that can host websites.
Command:
sudo dnf install nginx
This installs nginx on the Linux machine.

---

## Step 4: Start nginx
Command:
sudo systemctl start nginx
systemctl is used to manage services in Linux.

---

## Step 5: Check if nginx is running
Command:
systemctl status nginx
If everything is working correctly you will see:
Active: active (running)
This means the nginx server is running.

---

## Step 6: Open the website
i open a browser and visit:
http://server-ip
Then the nginx welcome page appeared.
This means the web server is working.

---

## What I learned
• How to connect to a Linux server  
• How to install software on Linux  
• How services work in Linux  
• How to run a web server  

I am currently learning Linux, cloud and DevOps step by step.


##DAY 2
## Linux Server Practice

### Directories Explored
- `/home` – location where user files and personal directories are stored.
- `/etc` – contains system configuration files used by services and applications.
- `/var/log` – directory where system logs and service logs are stored.
- `/var/log/nginx` – location of Nginx web server logs.

### Files Created
- Created new files using the `touch` command.
- Edited and added content to files using the `nano` text editor.

### Permission Changes
- Practiced changing file permissions using `chmod`.
- Example command: `chmod 755 script.sh`
- Learned how read (`r`), write (`w`), and execute (`x`) permissions control access to files.

### Nginx Logs Checked
- `/var/log/nginx/access.log` – records requests made to the web server.
- `/var/log/nginx/error.log` – records errors or problems related to the web server.

### Learning Points
- Understanding the Linux filesystem structure.
- Creating and editing files using terminal commands.
- Managing file permissions and executable files.
- Understanding how services like Nginx store logs.
- Inspecting web server activity using log files.
