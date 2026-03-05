# GitHub Actions – CI/CD Fundamentals

## 1. What is CI/CD

### Continuous Integration (CI)

Continuous Integration means **automatically building and testing code whenever changes are pushed to a repository**.

Example flow:

```
Developer pushes code
        ↓
CI pipeline runs
        ↓
Code is built
        ↓
Tests run automatically
```

**Benefits**

* Detect bugs early
* Improve code quality
* Faster development

---

### Continuous Delivery / Continuous Deployment (CD)

CD automatically **deploys the application after CI passes**.

**Continuous Delivery**

Deployment is ready but requires **manual approval**.

**Continuous Deployment**

Deployment happens **automatically without manual steps**.

Example:

```
Code pushed
↓
Build
↓
Test
↓
Deploy to server
```

---

# 2. What is GitHub Actions

GitHub Actions is a **CI/CD automation tool integrated with GitHub**.

It allows you to:

* Build code
* Run tests
* Deploy applications
* Automate workflows

Workflows are configured using **YAML files**.

Workflow location inside repository:

```
.github/workflows/
```

Example:

```
.github/workflows/ci.yml
```

---

# 3. Key Components of GitHub Actions

## Workflow

A **workflow** is an automated process defined in YAML.

Example tasks:

* Build project
* Run tests
* Deploy application

Example workflow file:

```
.github/workflows/build.yml
```

---

## Event

Events **trigger workflows**.

Common events:

| Event             | Description                            |
| ----------------- | -------------------------------------- |
| push              | Trigger when code is pushed            |
| pull_request      | Trigger when a pull request is created |
| schedule          | Run workflow at a scheduled time       |
| workflow_dispatch | Manual workflow trigger                |

Example:

```yaml
on: push
```

---

## Job

A **job** is a set of steps that run on the same runner.

Examples:

* Build job
* Test job
* Deploy job

Jobs can run:

* Sequentially
* In parallel

---

## Step

A **step** is an individual task inside a job.

Examples:

* Install dependencies
* Run tests
* Build application

Example:

```yaml
steps:
  - name: Install dependencies
    run: npm install
```

---

## Runner

A **runner** is the machine that executes the workflow.

GitHub provides hosted runners such as:

```
ubuntu-latest
windows-latest
macos-latest
```

Example:

```yaml
runs-on: ubuntu-latest
```

---

# 4. Basic GitHub Actions Workflow Example

Workflow file:

```
.github/workflows/ci.yml
```

Example workflow:

```yaml
name: CI Pipeline

on: push

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
```

Workflow flow:

```
Push code
↓
Workflow triggered
↓
Runner starts
↓
Steps executed
```

---

# 5. Using GitHub Actions

GitHub provides many **pre-built reusable actions**.

Examples:

```
actions/checkout
actions/setup-node
actions/setup-python
```

Example usage:

```yaml
uses: actions/checkout@v4
```

This action **checks out the repository code into the runner**.

---

# 6. Environment Variables

Environment variables store **configuration values** used in workflows.

Example:

```yaml
env:
  NODE_ENV: production
```

Using environment variables:

```yaml
run: echo $NODE_ENV
```

---

# 7. Secrets in GitHub Actions

Secrets store **sensitive data securely**.

Examples:

* API keys
* Passwords
* Tokens

Add secrets in:

```
Repository Settings
→ Secrets and Variables
→ Actions
```

Using a secret:

```yaml
${{ secrets.API_KEY }}
```

---

# 8. Matrix Strategy

Matrix allows running jobs on **multiple environments**.

Example:

```yaml
strategy:
  matrix:
    node-version: [16, 18]
```

This will run tests for:

```
Node.js 16
Node.js 18
```

---

# 9. Artifacts

Artifacts are files generated during workflows and stored for later use.

Examples:

* Build files
* Test reports
* Logs

Example:

```yaml
uses: actions/upload-artifact@v4
```

Artifacts help share files between jobs or download them later.

---

# 10. GitHub Actions Workflow Flow

Typical CI/CD pipeline:

```
Developer pushes code
        ↓
GitHub event triggers workflow
        ↓
Runner starts
        ↓
Jobs execute
        ↓
Steps run
        ↓
Tests pass
        ↓
Deployment happens
```

---

# 11. Advantages of GitHub Actions

* Built directly into GitHub
* Easy YAML configuration
* Large marketplace of reusable actions
* Supports CI/CD pipelines
* Works with Docker, Kubernetes, and cloud platforms

---

# 12. Common Use Cases

GitHub Actions is commonly used for:

```
CI pipelines
Code testing
Docker builds
Cloud deployment
Automation tasks
```

Example workflow:

```
Build Docker image
Push image to Docker Hub
Deploy application
```

---

# 13. GitHub Actions vs Jenkins

| Feature       | GitHub Actions            | Jenkins                     |
| ------------- | ------------------------- | --------------------------- |
| Setup         | Easy                      | Complex                     |
| Integration   | Native GitHub integration | Requires plugins            |
| Configuration | YAML workflows            | Pipeline scripts            |
| Maintenance   | Minimal                   | Requires server maintenance |

---

# Key Points to Remember

* GitHub Actions uses **YAML workflows**
* Workflows are triggered by **events**
* Jobs run on **runners**
* Steps execute tasks
* Secrets store sensitive data securely

---

# Conclusion

GitHub Actions is a powerful CI/CD automation tool that integrates directly with GitHub.
By understanding workflows, jobs, steps, and events, developers can automate building, testing, and deploying applications efficiently.
