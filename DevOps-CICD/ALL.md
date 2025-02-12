Here’s an overview of the topics you requested:

---

## **1. Git**
Git is a **distributed version control system (VCS)** that allows developers to track code changes, collaborate, and manage source code efficiently.

### **Basic Git Commands**
| Command | Description |
|---------|------------|
| `git init` | Initializes a new Git repository. |
| `git clone <repo-url>` | Clones a remote repository. |
| `git add <file>` | Stages changes for commit. |
| `git commit -m "message"` | Commits changes to the repository. |
| `git push origin <branch>` | Pushes local changes to a remote branch. |
| `git pull origin <branch>` | Pulls the latest changes from a remote branch. |
| `git branch` | Lists available branches. |
| `git checkout -b <new-branch>` | Creates and switches to a new branch. |

---

## **2. Jenkins**
Jenkins is an **open-source automation server** used for CI/CD (Continuous Integration and Continuous Deployment).

### **Jenkins Key Features**
- **Pipeline as Code**: Uses `Jenkinsfile` to define CI/CD pipelines.
- **Plugins**: Supports hundreds of plugins for integrations.
- **Distributed Builds**: Uses master-agent architecture for scalability.

### **Jenkins Pipeline Example**
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}
```

---

## **3. Docker**
Docker is a **containerization platform** that allows applications to run in isolated environments.

### **Docker Basic Commands**
| Command | Description |
|---------|------------|
| `docker pull <image>` | Pulls an image from Docker Hub. |
| `docker build -t myapp .` | Builds an image from a Dockerfile. |
| `docker run -d -p 8080:80 myapp` | Runs a container from an image. |
| `docker ps` | Lists running containers. |
| `docker stop <container-id>` | Stops a running container. |
| `docker rm <container-id>` | Removes a container. |

### **Dockerfile Example**
```dockerfile
FROM openjdk:11
COPY app.jar /app.jar
CMD ["java", "-jar", "/app.jar"]
```

---

## **4. GitHub Actions**
GitHub Actions is a **CI/CD tool** that automates workflows within GitHub.

### **GitHub Actions Workflow Example**
```yaml
name: CI Pipeline
on:
  push:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v3
      - name: Setup Java
        uses: actions/setup-java@v3
        with:
          java-version: '11'
      - name: Build
        run: mvn clean package
```

---

## **5. Reusable Workflows & Composite Actions**
### **Reusable Workflow Example**
```yaml
name: Reusable Workflow
on:
  workflow_call:
    inputs:
      env:
        required: true
        type: string
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Run Tests
        run: echo "Running tests in ${{ inputs.env }}"
```

### **Composite Action Example**
```yaml
name: "My Composite Action"
runs:
  using: "composite"
  steps:
    - name: Run a script
      run: echo "Hello from Composite Action"
      shell: bash
```

---

## **6. Application-Level Certificates**
Certificates are used for **secure communication (SSL/TLS)** in applications.

### **How Certs Work at the Application Level**
- **Self-signed or CA-signed certificates** are used for authentication and encryption.
- Certificates are stored in **keystores** (Java - `JKS`, Kubernetes - `Secrets`).
- **TLS Handshake**: Ensures encrypted communication.
- **Cert Renewal**: Automated via **Cert Manager, Let's Encrypt, or manual renewal**.

### **Kubernetes Secret for TLS**
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: tls-secret
type: kubernetes.io/tls
data:
  tls.crt: BASE64_ENCODED_CERT
  tls.key: BASE64_ENCODED_KEY
```

---

## **7. Elasticsearch Basics**
Elasticsearch is a **distributed search and analytics engine** used for log storage and retrieval.

### **Key Features**
- **Full-text search**: Fast searching across large datasets.
- **RESTful API**: Uses JSON-based queries.
- **Kibana Integration**: Visualizes Elasticsearch data.

### **Basic Elasticsearch Query**
```json
GET /my-index/_search
{
  "query": {
    "match": {
      "message": "error"
    }
  }
}
```

---

## **8. Shell Scripting Basics**
Shell scripting automates system administration tasks.

### **Basic Shell Script**
```bash
#!/bin/bash
echo "Hello, World!"
```

### **Useful Shell Commands**
| Command | Description |
|---------|------------|
| `ls` | Lists files in a directory. |
| `grep` | Searches for a pattern in files. |
| `awk` | Processes text data. |
| `sed` | Edits text streams. |

---

## **9. Python Basics**
Python is widely used in **automation, scripting, and web development**.

### **Basic Python Script**
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("DevOps"))
```

---

## **10. Groovy Basics**
Groovy is used in **Jenkins pipelines** and scripting.

### **Groovy Script Example**
```groovy
def greet(name) {
    return "Hello, ${name}!"
}
println(greet("DevOps"))
```

---

## **11. YAML Basics**
YAML (Yet Another Markup Language) is used for **configuration files** in Kubernetes, GitHub Actions, and CI/CD tools.

### **Example YAML File**
```yaml
name: DevOpsPipeline
stages:
  - build
  - test
  - deploy
```

---

### **Summary**
| Technology | Purpose |
|------------|---------|
| **Git** | Version control |
| **Jenkins** | CI/CD automation |
| **Docker** | Containerization |
| **GitHub Actions** | CI/CD within GitHub |
| **Reusable Workflows** | Modular pipeline execution |
| **Certificates** | Secure communication |
| **Elasticsearch** | Log storage and search |
| **Shell Scripting** | Automation scripts |
| **Python** | Programming and scripting |
| **Groovy** | Jenkins pipeline scripting |
| **YAML** | Configuration files |

Would you like in-depth explanations or hands-on examples for any of these topics? 🚀