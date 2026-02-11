# Devops-Containerisation

## Experiment 1

Comparison of Virtual Machines (VMs) and Containers using Ubuntu and Nginx

#### _NOTE_

This experiment is performed on a **MAC OS** system - _Apple Silcon M2_

### Objective 

To understand the conceptual and practical differences between Virtual Machines and Containers.

1. To install and configure a Virtual Machine using VirtualBox and Vagrant on Windows.
2. To install and configure Containers using Docker Desktop on macOS.
3. To deploy an Ubuntu-based Nginx web server in both environments.
4. To compare resource utilization, performance, and operational characteristics of VMs and Containers.

### Steps - _All the Steps are for Mac Users_

#### Docker Setup

1. Install Docker Desktop for Mac,
Docker Desktop was downloaded and installed from the official Docker website.<br>
Since macOS supports Docker natively, WSL is not required.
 ![Docker Installation](images/dockerInstallation.png)
2. Open Docker Desktop Application on your Mac from selecting it from applications.
![Openn Docker Desktop](images/OpenDockerDesktop.png)
3. Verify your Docker installation by runnung the command _docker --version_.<br>
You can see _Containers : 3_ in the output and also the _docker version_.
![VerifyInstallation](images/VerifyInstallation.png)

#### Pull Nginx Image

4. Command : _docker pull nginx_. This downloads the official Nginx image from Docker Hub.
![PullNgnix](images/pullngnix.png)

#### Run Nginx Container

5. Command : _docker run -d -p 8080:80 --name nginx-container nginx_<br>
- `-d` → Run in detached mode  
- `-p 8080:80` → Map port 8080 (host) to port 80 (container)  
- `--name nginx-container` → Container name  
- `nginx` → Image name
![runngnix](images/runngnix.png)


## TERMINOLOGIES 

1. What is ngnix ? <br>
   ngnix is a software 
   



