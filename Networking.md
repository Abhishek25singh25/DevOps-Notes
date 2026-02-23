# Networking Fundamentals

Networking is a core concept in DevOps because applications, servers, containers, and cloud systems communicate over networks.

Understanding networking helps in debugging connectivity issues, configuring servers, and managing cloud infrastructure.

---

## What is Networking?

Networking is the process of connecting computers and devices so they can communicate and share data.

In DevOps, networking is used for:

- Server communication
- API communication
- Database connections
- Container networking
- Cloud infrastructure

---

## IP Address

An IP address uniquely identifies a device on a network.

Types:

Public IP – Accessible over the internet  
Private IP – Used inside internal networks  

Example:
192.168.x.x (Private IP)

---

## Port

A port is a communication endpoint on a server.

Common Ports:

22 – SSH  
80 – HTTP  
443 – HTTPS  
3306 – MySQL  
5432 – PostgreSQL  

Ports allow multiple services to run on the same machine.

---

## DNS (Domain Name System)

DNS converts domain names into IP addresses.

Example:

google.com → 142.250.x.x

Without DNS, we would need to remember IP addresses.

---

## Protocols

HTTP – Hypertext Transfer Protocol  
HTTPS – Secure HTTP  
TCP – Transmission Control Protocol  
UDP – User Datagram Protocol  
FTP – File Transfer Protocol  

TCP ensures reliable communication.  
UDP is faster but does not guarantee delivery.

---

## OSI Model (Basic Understanding)

1. Physical  
2. Data Link  
3. Network  
4. Transport  
5. Session  
6. Presentation  
7. Application  

For DevOps, focus mainly on:

- Network Layer (IP)
- Transport Layer (TCP/UDP)
- Application Layer (HTTP, HTTPS)

---

## Important Networking Commands (Linux)

ip a – Show IP address  
ping – Test connectivity  
netstat – Show network connections  
ss – Socket statistics  
curl – Send HTTP request  
traceroute – Show network path  

These commands help in debugging production issues.

---

## What is a Firewall?

A firewall controls incoming and outgoing traffic based on rules.

Example:

Allow port 22 for SSH  
Allow port 80 for HTTP  

Firewalls protect servers from unauthorized access.

---

## What is NAT?

Network Address Translation allows private IP addresses to communicate with public networks.

Used heavily in cloud environments.

---

## Why Networking is Important in DevOps

- Debugging server issues
- Configuring cloud infrastructure
- Managing container communication
- Setting up load balancers
- Handling security rules

Without networking knowledge, DevOps troubleshooting becomes very difficult.
