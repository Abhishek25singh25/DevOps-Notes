# Linux Advanced

Linux Advanced covers deeper system-level concepts required for DevOps and production environments.

These concepts help in managing servers, debugging issues, and maintaining system stability.

---

## File Permissions (Advanced)

Each file has:

- Owner
- Group
- Others

Permission numeric system:

4 = Read  
2 = Write  
1 = Execute  

Example:

chmod 755 script.sh

7 = 4 + 2 + 1 (rwx)  
5 = 4 + 1 (r-x)

---

## Special Permissions

### SUID
Allows a user to run a file with the file owner's permissions.

### SGID
Allows execution with group permissions.

### Sticky Bit
Used mainly in shared directories like /tmp.

---

## Process Management (Advanced)

### Background Processes

command &

### Bring to foreground

fg

### List jobs

jobs

### Kill by process ID

kill -9 PID

Understanding process control is important for server management.

---

## System Monitoring

### CPU Usage
top  
htop  

### Memory Usage
free -m  

### Disk Usage
df -h  
du -sh  

Monitoring ensures system performance and stability.

---

## Networking Commands in Linux

ip a – Show IP address  
netstat – Show active connections  
ss – Socket statistics  
ping – Check connectivity  
curl – Make HTTP request  

---

## Environment Variables

View variables:

printenv

Set variable:

export VAR_NAME=value

Environment variables are important for application configuration.

---

## Services Management (Systemd)

Start service:

sudo systemctl start service-name

Stop service:

sudo systemctl stop service-name

Check status:

sudo systemctl status service-name

Enable at boot:

sudo systemctl enable service-name

Service management is essential in production servers.

---

## Crontab (Task Scheduling)

Open crontab:

crontab -e

Example schedule:

* * * * * command

Format:
Minute Hour Day Month Weekday

Cron jobs are used for automation tasks.

---

## SSH (Secure Shell)

Connect to remote server:

ssh user@ip-address

SSH is used to manage remote servers securely.

---

## Why Linux Advanced is Important for DevOps

- Managing production servers
- Debugging performance issues
- Automating scheduled tasks
- Managing services and system processes
- Handling security permissions

Advanced Linux knowledge separates beginners from serious DevOps engineers.
