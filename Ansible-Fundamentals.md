# Ansible – Fundamentals

---

## 1. What is Ansible

Ansible is a configuration management and automation tool.

It is used to automate:

* Server configuration
* Application deployment
* Infrastructure management

Ansible is **agentless**, meaning no software is required on target machines.

---

## 2. Why Use Ansible

* Simple and easy to learn
* Agentless architecture
* Uses SSH for communication
* Reduces manual work
* Ensures consistency

---

## 3. Ansible Architecture

Ansible works in a **control node → managed nodes** model.

* Control Node → where Ansible is installed
* Managed Nodes → target machines
* Inventory → list of servers

---

## 4. Inventory

Inventory is a file that contains details of target systems.

* Can be static or dynamic
* Organized using groups

Example:

* web servers
* database servers

---

## 5. Modules

Modules are small programs that perform tasks.

* File operations
* Package installation
* Service management

Examples:

* apt
* yum
* copy
* service

---

## 6. Ad-hoc Commands

Ad-hoc commands are one-line commands used for quick tasks.

* Useful for testing
* No need to write playbooks

Example tasks:

* Ping servers
* Install packages

---

## 7. Playbooks

Playbooks are YAML files used to define automation tasks.

* Written in YAML format
* Easy to read and write
* Execute multiple tasks

---

## 8. YAML Basics

YAML is a human-readable data format.

* Uses indentation
* Key-value pairs
* No brackets like JSON

---

## 9. Tasks

Tasks define actions in a playbook.

* Each task runs a module
* Executed in sequence

---

## 10. Handlers

Handlers are special tasks triggered by changes.

* Run only when notified
* Used for restarting services

---

## 11. Variables

Variables store values for reuse.

* Improve flexibility
* Avoid hardcoding

---

## 12. Facts

Facts are system information gathered by Ansible.

* IP address
* OS details
* Memory

---

## 13. Conditionals

Conditionals control execution using conditions.

* Based on variables or facts

---

## 14. Loops

Loops are used to repeat tasks.

* Avoid repetition
* Work with lists

---

## 15. Roles

Roles organize playbooks into a structured format.

* Improve reusability
* Keep code clean

Structure includes:

* tasks
* handlers
* variables
* templates

---

## 16. Templates

Templates use Jinja2 for dynamic configuration.

* Create dynamic files
* Replace variables

---

## 17. Tags

Tags allow selective execution of tasks.

* Run specific parts of playbook
* Useful for debugging

---

## 18. Ansible Vault

Ansible Vault is used to encrypt sensitive data.

* Protect passwords and secrets

---

## 19. Error Handling

Ansible provides error handling mechanisms.

* ignore_errors
* retries

---

## 20. Idempotency

Ansible ensures idempotency.

* Same result even after multiple runs
* No duplicate changes

---

## Key Points to Remember

* Ansible is agentless
* Uses SSH for communication
* Playbooks are written in YAML
* Modules perform tasks
* Roles improve structure

---

## Conclusion

Ansible simplifies automation by making infrastructure management easy, consistent, and scalable.

---
