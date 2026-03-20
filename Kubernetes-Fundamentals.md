# Kubernetes – Fundamentals (Theory Notes)

---

# 1. What is Kubernetes

Kubernetes is a **container orchestration platform** used to manage, deploy, and scale containerized applications automatically.

It helps in handling multiple containers efficiently in production environments.

---

# 2. Why Kubernetes is Needed

When applications are containerized using Docker, managing them manually becomes difficult.

Kubernetes solves this problem by:

* Automating deployment
* Managing scaling
* Handling failures (self-healing)
* Providing load balancing

---

# 3. Kubernetes Cluster

A Kubernetes cluster is a group of machines (nodes) that run applications.

It has two main parts:

* Control Plane
* Worker Nodes

---

# 4. Control Plane (Master)

The control plane manages the entire cluster.

Main components:

* API Server → Entry point for all requests
* Scheduler → Assigns Pods to nodes
* Controller Manager → Maintains desired state

---

# 5. Worker Node

Worker nodes run the actual applications.

Main components:

* Kubelet → Communicates with control plane
* Container Runtime → Runs containers
* Kube-proxy → Handles networking

---

# 6. Pod

A Pod is the **smallest unit in Kubernetes**.

* It contains one or more containers
* Pods are created and managed by Kubernetes

---

# 7. Deployment

Deployment is used to manage Pods.

* Ensures the desired number of Pods are running
* Provides scaling and updates

---

# 8. Service

Service is used to expose Pods to users.

* Provides stable IP address
* Load balances traffic

---

# 9. Scaling

Scaling means increasing or decreasing the number of Pods.

Types:

* Manual scaling
* Automatic scaling

---

# 10. Rolling Updates

Rolling update allows updating applications without downtime.

* New Pods are created
* Old Pods are removed gradually

---

# 11. ConfigMap

ConfigMap stores non-sensitive configuration data.

Example uses:

* Environment variables
* App configuration

---

# 12. Secret

Secrets store sensitive data securely.

Examples:

* Passwords
* API keys

---

# 13. Namespace

Namespace is used to organize resources inside a cluster.

It helps in separating environments like:

* Development
* Testing
* Production

---

# 14. Kubernetes Workflow

Typical workflow:

* Write configuration (YAML file)
* Apply using kubectl
* Kubernetes creates resources
* Application starts running

---

# 15. Key Features of Kubernetes

* Auto scaling
* Self-healing (restart failed Pods)
* Load balancing
* Automated deployment

---

# 16. Advantages

* High availability
* Efficient resource usage
* Easy deployment and management
* Suitable for microservices

---

# 17. Use Cases

* Microservices architecture
* Cloud-native applications
* Large-scale distributed systems

---

# Key Points to Remember

* Pod is the smallest unit
* Deployment manages Pods
* Service exposes application
* Kubernetes automates everything

---

# Conclusion

Kubernetes is a powerful platform for managing containerized applications and is widely used in modern DevOps practices.
