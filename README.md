## Day 1 - Linux Server Setup (Learning Project)
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


## DAY 2 - Linux Server Practice

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


## DAY 3 - Processes and Services

### Goal
Understand running processes and how to manage services like nginx.

### Steps
- Checked running processes using `ps aux`
- Monitored system activity using `top`
- Started, stopped, and restarted nginx using `systemctl`
- Observed logs in `/var/log/nginx`

### What I Learned
- How to see running processes in the system
- Difference between `ps` (snapshot) and `top` (live view)
- How to manage services using:
  - `start`
  - `stop`
  - `restart`
- Logs help understand what is happening inside the server
- When nginx is stopped, the website does not open
- When nginx is started again, the website becomes accessible


## Day 4 – Networking Basics

### Goal
Understand basic networking and how server responds to requests.

### Steps
- Checked IP address using `ip a` and `curl ifconfig.me`
- Checked open ports using `ss -tuln`
- Tested server response using `curl localhost`
- Modified website content in nginx default page
- Stopped and started nginx service to observe behavior

### What I Learned
- Difference between private IP and public IP
- How to check if a service is listening on a port
- How to test server response using curl
- How web server serves content from files
- When nginx is stopped, website does not load
- When nginx is started, website becomes accessible


## Day 5 – Users and Permissions

### Goal
Understand users, permissions, and access control in Linux.

### Steps
- Created a new user using `useradd`
- Set password using `passwd`
- Switched users using `su`
- Tested restricted access to files and directories
- Changed file ownership using `chown`
- Modified permissions using `chmod`
- Broke access by removing permissions and then fixed it

### What I Learned
- Linux has multiple users with different access
- File owner and root can control permissions
- Permissions (r, w, x) decide what a user can do
- Used `chown` to change owner and `chmod` to change permissions
- Removing permissions blocks access
- Permissions can be fixed if something breaks


## Day 6 – Package Management and Services

### Goal
Learn how to install, update, and manage software and services.

### Steps
- Updated system packages using `dnf update`
- Installed and removed software using `dnf install` and `dnf remove`
- Installed Apache web server (`httpd`)
- Faced port conflict when both nginx and httpd tried to use port 80
- Stopped nginx before starting httpd
- Switched between nginx and httpd services

### What I Learned
- `dnf` is used to install, update, and remove software
- Software must be installed using correct package names (apache = httpd)
- Only one service can run on a port at a time
- If port is busy, service will not start
- Need to stop one service before starting another
- Can switch between services based on need


## Day 7 – ssh and remote access

### Goal
Understand SSH and how to access a server remotely.

### Steps
- installed ssh service
- Connected to localhost using SSH
- create a new user
- Tested remote login with new user
- Stopped SSH service and faced connection issue
- Restarted SSH service to fix the problem

### What I Learned
- SSH is used to connect to a server remotely
- Can log in using username and password or key
- Different users can access the same server
- If SSH service stops, remote access fails
- Restarting SSH service restores access
