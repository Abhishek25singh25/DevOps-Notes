# Kubernetes – Advanced Concepts  

---

# 1. What is Advanced Kubernetes  

Advanced Kubernetes focuses on managing **production-level applications** with better scalability, security, and performance.  

It helps in building reliable and efficient systems.  

---

# 2. StatefulSet  

StatefulSet is used for **stateful applications** like databases.  

* Each Pod has a unique identity  
* Data is preserved even after restart  
* Pods are created in sequence  

---

# 3. DaemonSet  

DaemonSet ensures that a Pod runs on **every node** in the cluster.  

* Used for monitoring and logging  
* Runs automatically on new nodes  

---

# 4. Job  

Job is used to run a task **one time or until completion**.  

* Suitable for batch processing  
* Stops after task is completed  

---

# 5. CronJob  

CronJob runs Jobs on a **fixed schedule**.  

* Works like cron in Linux  
* Used for backups and automation  

---

# 6. Ingress  

Ingress is used to manage **external access to services**.  

* Provides HTTP/HTTPS routing  
* Acts as a load balancer  
* Requires Ingress Controller  

---

# 7. Horizontal Pod Autoscaler (HPA)  

HPA automatically scales Pods based on load.  

* Uses CPU or memory usage  
* Increases or decreases Pods dynamically  

---

# 8. Vertical Pod Autoscaler (VPA)  

VPA adjusts **resource limits of containers**.  

* Optimizes CPU and memory  
* Improves performance  

---

# 9. Persistent Volume (PV)  

PV is a **storage resource** in Kubernetes.  

* Independent of Pods  
* Data remains safe even if Pod is deleted  

---

# 10. Persistent Volume Claim (PVC)  

PVC is used to request storage.  

* Connects Pods with storage  
* Makes storage easy to use  

---

# 11. Storage Classes  

StorageClass defines **types of storage**.  

* Enables dynamic storage creation  
* Used in cloud environments  

---

# 12. RBAC (Role-Based Access Control)  

RBAC controls **permissions in Kubernetes**.  

* Defines who can access what  
* Improves security  

---

# 13. Network Policies  

Network Policies control **network traffic between Pods**.  

* Restricts unwanted communication  
* Adds security layer  

---

# 14. Helm  

Helm is a **package manager for Kubernetes**.  

* Uses charts  
* Simplifies deployment  
* Reusable configurations  

---

# 15. Operators  

Operators automate **complex application management**.  

* Manage stateful apps  
* Reduce manual work  

---

# 16. Service Mesh  

Service Mesh manages **communication between services**.  

* Controls traffic  
* Adds security  
* Provides monitoring  

---

# 17. Monitoring & Logging  

Used to track system performance.  

* Monitoring tools collect metrics  
* Logging tools store logs  

---

# 18. Kubernetes Security  

Security ensures safe cluster operations.  

* Use RBAC for access control  
* Use Secrets for sensitive data  
* Use Network Policies  

---

# 19. High Availability  

High availability ensures system is always running.  

* Multiple nodes  
* Load balancing  
* Failover support  

---

# 20. Key Points to Remember  

* StatefulSet for stateful apps  
* HPA for auto scaling  
* PV/PVC for storage  
* RBAC for security  
* Helm for easy deployment  

---

# Conclusion  

Advanced Kubernetes helps in managing large-scale applications efficiently with better performance, security, and automation.  
