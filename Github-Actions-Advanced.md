# GitHub Actions – Advanced Concepts

---

# 1. Matrix Strategy

## What is Matrix Strategy

Matrix strategy allows running a job **multiple times with different configurations automatically**.

Instead of writing separate jobs, GitHub creates them for you.

---

## Example Flow

```
Job defined once
        ↓
Matrix expands configurations
        ↓
Multiple jobs run in parallel
```

---

## Basic Example

```yaml
strategy:
  matrix:
    node-version: [16, 18]
```

This will run jobs for:

```
Node.js 16
Node.js 18
```

---

## Full Example

```yaml
name: Matrix Example

on: push

jobs:
  test:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node: [16, 18]

    steps:
      - uses: actions/checkout@v4

      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node }}

      - run: node -v
```

---

## Advantages

* Parallel execution
* Faster testing
* Multi-environment support

---

# 2. Docker Build and Push

## What is Docker in CI/CD

Docker is used to **package applications into containers** so they run the same everywhere.

---

## Flow

```
Code pushed
        ↓
Docker image built
        ↓
Image pushed to registry
```

---

## Basic Example

```yaml
- run: docker build -t my-app .
```

---

## Full Example

```yaml
name: Docker Pipeline

on: push

jobs:
  docker:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_TOKEN }}

      - name: Build and Push
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: myuser/my-app:latest
```

---

## Explanation

* Login action authenticates Docker Hub
* Build-push action builds and uploads image
* Tags define image name

---

## Best Practices

* Use version tags + latest
* Store credentials in secrets
* Use caching for faster builds

---

# 3. Self-Hosted Runners

## What are Self-Hosted Runners

Self-hosted runners are **your own machines** used to run workflows instead of GitHub servers.

---

## Flow

```
Workflow triggered
        ↓
Runs on your machine
        ↓
Execution completed
```

---

## Example

```yaml
jobs:
  build:
    runs-on: self-hosted

    steps:
      - run: echo "Running on self-hosted runner"
```

---

## Advantages

* Full control over environment
* Faster execution
* Custom tools installation

---

## Disadvantages

* Maintenance required
* Security responsibility

---

# 4. Job Dependencies

## What is Job Dependency

Jobs can depend on other jobs using `needs`.

---

## Example

```yaml
jobs:
  build:
    runs-on: ubuntu-latest

  test:
    needs: build
    runs-on: ubuntu-latest
```

---

## Flow

```
Build job
    ↓
Test job runs
```

---

## Benefit

Ensures correct order of execution.

---

# 5. Conditional Execution

## What is Conditional Execution

Allows running jobs or steps **only when a condition is true**.

---

## Example

```yaml
if: github.ref == 'refs/heads/main'
```

---

## Use Cases

* Deploy only on main branch
* Skip jobs for PRs

---

# 6. Caching

## What is Caching

Caching stores dependencies to **speed up future runs**.

---

## Example

```yaml
- uses: actions/cache@v3
  with:
    path: ~/.npm
    key: node-cache
```

---

## Benefit

* Faster builds
* Reduced install time

---

# 7. Artifacts (Advanced Use)

## What are Artifacts

Artifacts are files saved after workflow execution.

---

## Example

```yaml
- uses: actions/upload-artifact@v4
  with:
    name: build-files
    path: dist/
```

---

## Use Cases

* Store build outputs
* Share files between jobs

---

# 8. Advanced Pipeline Flow

## Example Flow

```
Push code
        ↓
Build & Test (Matrix)
        ↓
Docker Build & Push
        ↓
Deploy
```

---

## Full Example

```yaml
name: Advanced Pipeline

on:
  push:
    branches: [main]

jobs:

  test:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        python: [3.9, 3.10]

    steps:
      - uses: actions/checkout@v4
      - run: echo "Testing on Python ${{ matrix.python }}"

  docker:
    needs: test
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_TOKEN }}

      - uses: docker/build-push-action@v5
        with:
          push: true
          tags: my-app:latest
```

---

# 9. Advantages of Advanced Features

* Faster pipelines using parallel jobs
* Better scalability
* Real-world deployment support
* Flexible execution

---

# 10. Common Use Cases

```
Testing multiple environments
Docker image automation
Custom runner execution
Optimized CI/CD pipelines
```

---

# Key Points to Remember

* Matrix runs jobs in parallel
* Docker creates deployable images
* Self-hosted runners use your own machine
* Needs controls job order
* Cache improves speed

---

# Conclusion

Advanced GitHub Actions features help in building scalable, efficient, and production-ready CI/CD pipelines.
