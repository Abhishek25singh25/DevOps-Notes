# DevSecOps – Fundamentals and Implementation

---

# 1. What is DevSecOps

## Definition

DevSecOps means **integrating security into every stage of the DevOps pipeline**.

Instead of adding security at the end, it is included from the beginning.

---

## Flow

```id="devsec-flow"
Code written
        ↓
Security checks
        ↓
Build
        ↓
Test
        ↓
Deploy
```

---

## Key Idea

Security is **everyone’s responsibility**, not just the security team.

---

## Benefits

* Early detection of vulnerabilities
* Reduced security risks
* Faster and safer deployments
* Continuous monitoring

---

# 2. DevOps vs DevSecOps

| Feature  | DevOps    | DevSecOps        |
| -------- | --------- | ---------------- |
| Focus    | Speed     | Speed + Security |
| Security | End stage | Every stage      |
| Risk     | Higher    | Lower            |

---

# 3. Security in CI/CD Pipeline

## Where security is added

```id="pipeline-sec"
Code → Scan → Build → Scan → Deploy → Monitor
```

---

## Types of Security Checks

* Static code analysis (SAST)
* Dependency scanning
* Container scanning
* Runtime security

---

# 4. Static Code Analysis (SAST)

## What is SAST

Analyzing source code for vulnerabilities **without running it**.

---

## Example

```yaml id="sast-example"
- name: Run Code Scan
  run: echo "Scanning code for vulnerabilities"
```

---

## Tools

* SonarQube
* CodeQL
* ESLint (basic)

---

# 5. Dependency Scanning

## What is it

Checks libraries used in the project for known vulnerabilities.

---

## Example

```yaml id="dep-scan"
- run: npm audit
```

---

## Tools

* npm audit
* pip audit
* Snyk

---

# 6. Container Security (Docker Scan)

## What is it

Scans Docker images for vulnerabilities.

---

## Flow

```id="docker-sec"
Build image
        ↓
Scan image
        ↓
Push if safe
```

---

## Example (Trivy)

```yaml id="trivy-example"
- name: Scan Docker Image
  uses: aquasecurity/trivy-action@v0.20.0
  with:
    image-ref: my-app:latest
```

---

## Explanation

* Trivy scans for vulnerabilities
* Can fail pipeline if issues found

---

# 7. Secrets Management

## What are Secrets

Sensitive data such as:

* API keys
* Tokens
* Passwords

---

## Where stored

```id="secret-path"
GitHub Settings → Secrets → Actions
```

---

## Example

```yaml id="secret-use"
${{ secrets.API_KEY }}
```

---

## Best Practices

* Never hardcode secrets
* Use environment variables
* Rotate secrets regularly

---

# 8. Security Gates

## What are Security Gates

Conditions that **stop pipeline if security fails**.

---

## Example

```yaml id="gate"
if: failure()
```

---

## Use Case

* Stop deployment if vulnerability detected

---

# 9. DevSecOps Pipeline Example

## Flow

```id="full-sec-flow"
Push code
        ↓
SAST scan
        ↓
Dependency scan
        ↓
Build
        ↓
Docker scan
        ↓
Deploy
```

---

## Example Code

```yaml id="devsec-pipeline"
name: DevSecOps Pipeline

on: push

jobs:

  scan:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Dependency Scan
        run: pip install safety && safety check || true

  docker:
    needs: scan
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - run: docker build -t my-app .

      - name: Scan Image
        uses: aquasecurity/trivy-action@v0.20.0
        with:
          image-ref: my-app:latest
```

---

# 10. Advantages of DevSecOps

* Security integrated early
* Reduced vulnerabilities
* Faster secure deployments
* Better compliance

---

# 11. Common Tools

```id="tools"
SAST → SonarQube, CodeQL  
Dependency → Snyk, npm audit  
Container → Trivy  
Secrets → GitHub Secrets, Vault  
```

---

# 12. Real Use Cases

```id="usecase"
Secure CI/CD pipelines  
Automated vulnerability scanning  
Cloud deployment security  
Container security  
```

---

# Key Points to Remember

* Security is continuous
* Always scan before deploy
* Use secrets securely
* Automate everything

---

# Conclusion

DevSecOps ensures that security is built into every stage of the CI/CD pipeline, making applications safer and more reliable.

---

# #DevOps #DevSecOps #CICD #TrainWithShubham
