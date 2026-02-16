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

### Software and Hardware Requirements

#### Hardware

1. 64-bit system with virtualization support enabled in BIOS
2. Minimum 8 GB RAM (4 GB minimum acceptable)
3. Internet connection

#### Software : _MAC OS_

1. Oracle VirtualBox (Intel Macs only)
2. Vagrant
3. Docker Desktop 


### Theory 

#### Virtual Machine 

A Virtual Machine emulates a complete physical computer, including its own operating system kernel, hardware drivers, and user space. Each VM runs on top of a hypervisor.

#### Characteristics:

- Full OS per VM
- Higher resource usage
- Strong isolation
- Slower startup time

#### Container

Containers virtualize at the operating system level. They share the host OS kernel while isolating applications and dependencies in user space.

#### Characteristics:

- Shared kernel
- Lightweight
- Fast startup
- Efficient resource usage

## PART - A : Vagarant on MAC OS




## PART - B : Containers using Docker Desktop

### Steps - _All the Steps are for Mac Users_

#### Docker Setup

1. Install Docker Desktop for Mac,
Docker Desktop was downloaded and installed from the official Docker website.<br>
Since macOS supports Docker natively, WSL is not required.
 ![Docker Installation](images/dockerInstallation.png)
2. Open Docker Desktop Application on your Mac from selecting it from applications.
![Openn Docker Desktop](images/OpenDockerDesktop.png)
3. Verify your Docker installation by running the command `_docker --version_`<br>
You can see _Containers : 3_ in the output and also the `docker version`.
![VerifyInstallation](images/VerifyInstallation.png)

#### Pull Nginx Image

4. Command : `docker pull nginx_` This downloads the official Nginx image from Docker Hub.
![PullNgnix](images/pullngnix.png)

#### Run Nginx Container

5. Command : `docker run -d -p 8080:80 --name nginx-container nginx`<br>
- `-d` → Run in detached mode  
- `-p 8080:80` → Map port 8080 (host) to port 80 (container)  
- `--name nginx-container` → Container name  
- `nginx` → Image name
![runngnix](images/runngnix.png)


## TERMINOLOGIES 

1. What is ngnix ? <br>
   ngnix is a software 
   



