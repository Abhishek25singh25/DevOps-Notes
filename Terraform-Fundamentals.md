# Terraform – Basics & Advanced  

---

# 1. What is Terraform  

Terraform is an **Infrastructure as Code (IaC) tool** used to create, manage, and provision infrastructure automatically.  

It allows you to define infrastructure using code instead of manual setup.  

---

# 2. Why Terraform is Needed  

Managing infrastructure manually is time-consuming and error-prone.  

Terraform solves this by:  

* Automating infrastructure creation  
* Ensuring consistency  
* Enabling version control  
* Supporting multi-cloud environments  

---

# 3. Infrastructure as Code (IaC)  

IaC means managing infrastructure using code files.  

* Infrastructure becomes repeatable  
* Easy to track changes  
* Reduces manual errors  

---

# 4. Terraform Workflow  

Basic workflow:  

* Write configuration (.tf files)  
* Run `terraform init`  
* Run `terraform plan`  
* Run `terraform apply`  
* Use `terraform destroy` when needed  

---

# 5. Providers  

Providers are plugins that allow Terraform to interact with platforms.  

Examples:  

* AWS  
* Azure  
* Google Cloud  

---

# 6. Resources  

Resources define the actual infrastructure components.  

Examples:  

* EC2 instance  
* VPC  
* S3 bucket  

---

# 7. Variables  

Variables are used to make configurations dynamic.  

* Avoid hardcoding values  
* Improve reusability  

---

# 8. Outputs  

Outputs display useful information after execution.  

* Example: public IP, instance ID  

---

# 9. State File  

Terraform keeps track of infrastructure using a **state file**.  

* Stores current infrastructure state  
* Helps in planning changes  

---

# 10. Modules  

Modules are reusable pieces of Terraform code.  

* Helps in organizing code  
* Improves scalability  

---

# 11. Dependency Management  

Terraform automatically manages dependencies between resources.  

* Ensures correct order of execution  

---

# 12. Remote Backend  

Remote backend stores state file remotely.  

* Example: AWS S3  
* Enables team collaboration  
* Supports locking  

---

# 13. Workspaces  

Workspaces allow multiple environments using same code.  

* dev  
* staging  
* prod  

---

# 14. Data Sources  

Data sources fetch existing infrastructure details.  

* Example: existing VPC  

---

# 15. Terraform Functions  

Functions are used to manipulate data.  

* String functions  
* Numeric functions  

---

# 16. Advanced – Custom Modules  

Custom modules are user-defined reusable components.  

* Encapsulate logic  
* Improve maintainability  

---

# 17. Advanced – Registry Modules  

Terraform Registry provides pre-built modules.  

* Saves time  
* Standardized configurations  

---

# 18. Advanced – State Management  

Proper state management is critical.  

* Use remote backend  
* Enable state locking  
* Enable versioning  

---

# 19. Advanced – Provisioners  

Provisioners run scripts on resources.  

* Used for setup tasks  
* Example: install software  

---

# 20. Advanced – Lifecycle Rules  

Lifecycle rules control resource behavior.  

* prevent_destroy  
* create_before_destroy  

---

# 21. Advanced – Dynamic Blocks  

Dynamic blocks allow creating repeated nested blocks.  

* Useful for complex configurations  

---

# 22. Advanced – Multi-Environment Setup  

Use workspaces or separate configs.  

* Maintain isolation  
* Avoid conflicts  

---

# 23. Advanced – Security Best Practices  

* Do not store secrets in code  
* Use .gitignore for state files  
* Encrypt remote state  
* Use IAM roles  

---

# 24. Advanced – Best Practices  

* Use modules  
* Use proper file structure  
* Always run plan before apply  
* Keep code clean and readable  

---

# 25. Key Points to Remember  

* Terraform is declarative  
* State file is very important  
* Modules improve reusability  
* Workspaces manage environments  
* Remote backend is recommended  

---

# Conclusion  

Terraform is a powerful tool for managing infrastructure efficiently.  
From basic resource creation to advanced multi-environment setups, it plays a key role in modern DevOps practices.  
