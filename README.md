# Exercise 2.1 – Enterprise CI/CD Pipeline with GitHub Actions

## Overview

This project demonstrates a simplified enterprise-grade CI/CD pipeline using GitHub Actions. The pipeline automates building, testing, security scanning, artifact management, deployment simulation, health checks, rollback mechanisms, and notifications for a Flask application.

## Features

* Multi-stage CI/CD pipeline
* Automated build process
* Automated testing with Pytest
* Security scanning with Bandit (SAST)
* Matrix testing across multiple Python versions
* Artifact generation and storage
* Simulated deployment stage
* Health check stage
* Automated rollback simulation
* Deployment notifications
* Simulated DAST security scan

---

## Project Structure

```text
exercise-2-1/
│
├── app.py
├── requirements.txt
├── test_app.py
│
└── .github/
    └── workflows/
        └── pipeline.yml
```

---

## Technologies Used

* Python 3
* Flask
* Pytest
* Bandit
* GitHub Actions

---

## Application

The Flask application exposes a simple endpoint:

```python
@app.route("/")
def home():
    return "CI/CD Pipeline Working"
```

---

## Running Locally

### Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/exercise-2-1.git
cd exercise-2-1
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Application

```bash
python app.py
```

Open your browser and visit:

```text
http://127.0.0.1:5000
```

Expected output:

```text
CI/CD Pipeline Working
```

---

## Running Tests

```bash
pytest
```

Expected result:

```text
1 passed
```

---

## CI/CD Pipeline Workflow

The pipeline automatically runs whenever code is pushed to the main branch.

### Pipeline Stages

#### 1. Build Stage

* Checks out source code
* Sets up Python
* Installs dependencies
* Creates application artifact

#### 2. Test Stage

* Executes automated tests
* Runs tests on:

  * Python 3.9
  * Python 3.10
  * Python 3.11

#### 3. Security Scan (SAST)

* Runs Bandit security analysis
* Scans source code for vulnerabilities

#### 4. Artifact Management

* Packages application files
* Uploads build artifact to GitHub Actions

#### 5. Deploy Stage

* Simulates application deployment

#### 6. Health Check

* Verifies deployment status

#### 7. Rollback Stage

* Executes rollback simulation if deployment validation fails

#### 8. Notification Stage

* Reports deployment success

#### 9. DAST Scan

* Simulates dynamic application security testing

---

## Pipeline Flow

```text
Push Code
   │
   ▼
Build
   │
   ▼
Test (3 Python Versions)
   │
   ▼
Security Scan
   │
   ▼
Artifact Upload
   │
   ▼
Deploy
   │
   ▼
Health Check
   │
 ┌─┴─────────┐
 │           │
Pass       Fail
 │           │
 ▼           ▼
Notify   Rollback
```

---

## Learning Objectives

This project demonstrates:

* CI/CD fundamentals
* GitHub Actions workflows
* Automated testing
* Security scanning
* Matrix builds
* Artifact management
* Deployment automation concepts
* Health monitoring
* Rollback strategies
* Enterprise pipeline design principles

---

## Author

Oluwaferanmi Dada

DevOps Engineering Internship – Exercise 2.1
