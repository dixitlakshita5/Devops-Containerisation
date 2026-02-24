# Devops-Containerisation

Name: Lakshita Dixit 
SAP : 500125823
School of Computer Science  
University of Petroleum and Energy Studies, Dehradun  

---

## EXPERIMENT – 4

## Dockerfile, .dockerignore, Tagging & Publishing
---

## Aim

To containerize applications using Docker, create and use Dockerfile and .dockerignore, build and tag Docker images, run containers, and publish images to Docker Hub.

---

## Objectives

- To understand the basic concepts of Docker and containerization.
- To create and use a Dockerfile to containerize a Python/Node.js application.
- To implement and understand the importance of the `.dockerignore` file.
- To build, tag, and manage Docker images and containers using Docker CLI commands.
- To publish Docker images to Docker Hub and understand the Docker development workflow.

---
## PART 1 : Containerizing a Python Flask Application Using Dockerfile

### REQUIREMENTS 

- macOS system
- Docker Desktop installed
- Terminal
- Internet connection

### THEORY

Docker is a containerization platform used to package applications with their dependencies.  

A Dockerfile is a text file containing instructions to build a Docker image.  

A Docker Image is a blueprint of the application.  

A Container is a running instance of the image.

### Step 1: Create Project Directory

- Open Terminal.

- Run the following commands:

```bash
mkdir my-flask-app
cd my-flask-app
```
### Step 2: Create Python Flask Application

- Create a new file:

```bash
touch app.py
```

- Open it using VS Code (if installed):

```bash
code .
```

- Now paste the following code inside app.py:

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello from Docker!"

@app.route('/health')
def health():
    return "OK"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

### Step 3: Create requirements.txt File

- This file contains project dependencies.

- Run:

```bash
touch requirements.txt
```

- Open it and add:

```text
Flask==2.3.3
```

### Step 4: Create Dockerfile

- Create Dockerfile (no extension):

```bash
touch Dockerfile
```

- Now paste this inside Dockerfile:

```dockerfile
# Use Python base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy requirements file
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY app.py .

# Expose port
EXPOSE 5000

# Run the application
CMD ["python", "app.py"]
```
### Step 5: Build Docker Image

- Now build the image:

```bash
docker build -t my-flask-app .
```

- Explanation:

  - docker build → builds the Docker image.
  - -t my-flask-app → assigns the name `my-flask-app` to the image.
  - . → indicates the current directory contains the Dockerfile.

- Wait until the build completes successfully.

### Step 6: Verify Image

- Run:

```bash
docker images
```

- You should see:

```text
my-flask-app   latest
```

### Step 7: Run the Container

- Run:

```bash
docker run -d -p 5000:5000 --name flask-container my-flask-app
```

- Explanation:

  - -d → runs the container in the background (detached mode).
  - -p 5000:5000 → maps container port 5000 to Mac port 5000.
  - --name → assigns the name `flask-container` to the container.
  - my-flask-app → specifies the Docker image to run.

### Step 8: Test Application

- Open browser and type:

```text
http://localhost:5000
```

- Output:

```text
Hello from Docker!
```

- Check health endpoint:

```text
http://localhost:5000/health
```

- Output:

```text
OK
```

### ✅ Step 9: Stop Container (After Testing)

```bash
docker stop flask-container
docker rm flask-container
```

## OUTPUT

The Flask application was successfully containerized and executed inside a Docker container.

## RESULT

The simple Python Flask application was successfully containerized using Dockerfile and executed on localhost.