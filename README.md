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


## Day 8 – Environment Variables

### Goal
Learn what environment variables are and how to use them.

### What I Did
- Created a variable:
  MY_CITY=kanina

- Checked the value:
  echo $MY_CITY

- Made it permanent using:
  nano ~/.bashrc

- Added this line:
  export MY_CITY="kanina"

- Applied changes:
  source ~/.bashrc

- Removed and added the variable again to practice

### What I Learned
- Variable = name that stores a value
- Use `$` to see value (echo $MY_CITY)
- `.bashrc` is used to save variables permanently
- `source ~/.bashrc` applies changes
- Small mistakes in `.bashrc` can cause errors


## Day 9 – Web Server Testing and Logs

### Steps
- Edited website using `nano`
- Refreshed browser to see changes
- Checked logs using `tail access.log`
- Stopped nginx and saw site stop
- Started nginx and site worked again

### What I Learned
- Website updates after file changes
- Logs show user requests
- If nginx stops, site stops
- Starting nginx restores site


## Day 10 – Disk Storage

### Steps
- Checked disk space using `df -h`
- Created a large file and observed disk usage increase
- Deleted the file and saw space get freed

### What I Learned
- Disk stores all files and data
- `df -h` shows total, used, and free space
- Creating files increases disk usage
- Deleting files frees up space


## Day 11 – Docker Basics

- Run a python app using docker 
- Installed Docker: `sudo dnf install docker`
- Started Docker: `sudo systemctl start docker`
- Ran Python container: `docker run -p 5000:5000 python`
- Started a server inside container and opened it in browser

### What I Learned
- Docker runs apps inside containers
- No need to install software on system
- Containers are isolated
- Ports allow access to container apps


## Day 12 - docker with custom website 

### steps
- what did i try 
- i tried to run my own html page using docker on my aws server 
- container started but the website was not opening in browser
- so i checked out and i faced issues like port already used, permission denied, Aws port closed
- i fixed them by stoping old containers, using sudo, and allowing the port in AWS security group.

### What i learned
- Running container is not enough, we need to manage ports and cloud network settings.


## Day 13 - docker image & container basics

- Today i created my own docker image using a dockerfile.
- I added an HTML file, build the image, and run it as a container.
- then i opened it in browser and saw my output.

### steps
- create index.html
- created dockerfile
- built image using: docker built -t myapp
- ran container: docker run -p 5000:5000 myapp
- opened browser: http://public ip:5000

### what i learned 
- dockerfile is used to build image
- image is used to create container
- container runs the application 


## Day 14 – Multi-Container Setup

### Steps
- Created two containers: one for database and one for application
- Connected both containers using container name
- Verified communication between app and database 

### What i learned 
- Multiple containers can work together as services
- Containers can communicate using names instead of IP
- Real applications use separate services (app + database)


## Day 15 - Docker compose + Aws 

### steps
- I created a simple html page and built a docker image using dockerfile.
- then i used docker-compose to run the container.
- I had to make sure ports were open and container was running properly
- i checked container status and verified ports using docker commands.

### what i learned 
- i learned that docker compose makes it easy to manage containers using one file and one command.


## Day 16 – Docker Revision and Practice

### Steps
- Revised Docker basics and commands
- Checked running containers:
  `sudo docker ps`
- Listed all containers:
  `sudo docker ps -a`
- Ran nginx container:
  `sudo docker run -d -p 8080:80 nginx`
- Ran redis container in custom network:
  `sudo docker run -d --name db --network mynet redis`
- Stopped container:
  `sudo docker stop <container_id>`
- Removed container:
  `sudo docker rm <container_id>`
- Checked networks:
  `sudo docker network ls`

### What I Learned
- Docker commands become easier with practice
- Containers can be fully managed from terminal
- Permission and name conflicts are common errors
- Using correct commands and sequence is important
- Hands-on practice improves understanding


## Day 17 - Docker project 

### Project structure 
- day17-project/
 ├── app/
 │   └── index.html
 ├── Dockerfile
 └── docker-compose.yml

### What i did 
- first i created a folder & a file using mkdir and file with nano index.html 
- Then i wrote HTML page in file
- Then i created Dockerfile  using nano Dockerfile
- After that i got an error my image is not ready so i created an image
- then used docker-compose to run container

### what i learned 
- How Dockerfile and docker-compose work together
- How to run project using one command
- Importance of project structure
