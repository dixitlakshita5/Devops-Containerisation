# 30-01-2026

## Topic: Docker Image Creation, Versioning, and Docker Hub Push

---

## Objective
To build Docker images using Dockerfile, run containers, modify Dockerfile to create new image versions, and push Docker images to Docker Hub.

---

## Tools Used
- Docker
- Docker Desktop
- macOS Terminal
- Java (OpenJDK 17)
- Docker Hub

---

## Theory
Docker allows applications to be packaged into images using a Dockerfile. These images can be versioned, executed as containers, and shared using Docker Hub. Versioning helps maintain multiple builds of the same application. Docker Hub acts as a centralized repository to store and distribute Docker images.

---

## Procedure

### Step 1: View Project Files
The project directory containing `Dockerfile` and `Hello.java` was verified.

![Project Files](./images/image1.jpeg)

---

### Step 2: Build Docker Image (Version 1.0)

```bash
docker build -t java-app:1.0 .
```
![](./images/image2.jpeg)

### Step 3: Run Docker Image (Version 1.0)
The Docker image built in the previous step was executed to verify its output.

```bash
docker run java-app:1.0
```
![](./images/image3.jpeg)
The container executed successfully and printed output.

### Step 4: Run Container in Interactive Mode
```bash
docker run -it java-app:1.0 bash
```
![](./images/image4.jpeg)
The container was accessed using an interactive shell.

### Step 5: Modify Dockerfile
![](./images/image5.jpeg)
The Dockerfile was edited to change the default command and application output.

### Step 6: Build Docker Image (Version 2.0)
```bash
docker build -t javaapp:2.0 -f second.Dockerfile .
```

A new version of the Docker image was created.

### Step 7: Run Docker Image Version 2.0
```bash
docker run javaapp:2.0
```
![](./images/image7.jpeg)
The output confirmed execution of the updated version.

### Step 8: Push Docker Image to Docker Hub
```bash
docker login
docker tag java-app:1.0 lakshitadixit/java-app:1.0
docker push lakshitadixit/java-app:1.0
```
![](./images/image6.jpeg)
![](./images/image8.jpeg)

The Docker image was successfully pushed to Docker Hub and later pulled.