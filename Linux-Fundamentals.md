# Linux Basics

Linux is the backbone of modern infrastructure.  
Most production servers, cloud environments, containers, and DevOps tools run on Linux.

Strong Linux fundamentals are essential for any DevOps Engineer.

---

## What is Linux?

Linux is an open-source, Unix-like operating system.

It is:

- Stable
- Secure
- Highly customizable
- Widely used in servers and cloud environments

Popular distributions:

- Ubuntu
- CentOS
- Debian
- Red Hat

---

## Linux File System Structure

Linux follows a hierarchical filesystem.

Important directories:

/ – Root directory  
/home – User home directories  
/etc – Configuration files  
/var – Logs and variable files  
/usr – User programs and libraries  
/bin – Essential system binaries  
/tmp – Temporary files  

Understanding the filesystem is critical for debugging and system management.

---

## Basic Linux Commands

### Navigation

pwd – Print current directory  
ls – List files and directories  
cd – Change directory  

### File & Directory Management

mkdir – Create directory  
rm – Remove file or directory  
cp – Copy files  
mv – Move or rename files  
touch – Create empty file  

---

## File Permissions

Every file has:

- Owner
- Group
- Others

Permission types:

r – Read  
w – Write  
x – Execute  

Example:

chmod 755 script.sh

Permission breakdown:

7 = read + write + execute  
5 = read + execute  

Understanding permissions is crucial in DevOps environments.

---

## Process Management

ps – View running processes  
top – Real-time process monitoring  
htop – Advanced process monitoring  
kill – Terminate process  

Processes help understand system load and performance.

---

## Package Management (Ubuntu)

apt update – Update package list  
apt upgrade – Upgrade packages  
apt install package-name – Install package  

Package management allows software installation and updates.

---

## User & Group Management

useradd username – Create user  
passwd username – Set password  
usermod – Modify user  
groupadd groupname – Create group  

User management is important for system security.

---

## Logs in Linux

Log files are usually stored in:

/var/log

Common log files:

syslog  
auth.log  
kern.log  

Logs are essential for debugging production systems.

---

## Why Linux is Important in DevOps

- Most cloud servers run Linux
- Docker runs on Linux
- Kubernetes runs on Linux
- CI/CD agents often run on Linux

Strong Linux knowledge = Strong DevOps foundation.
