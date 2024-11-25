# Cloud-Computing

Cloud computing is the delivery of computing services—including servers, storage, databases, networking, software, analytics, and intelligence—over the Internet ("the cloud"). This allows for faster innovation, flexible resources, and economies of scale.

![image](https://github.com/user-attachments/assets/0b831d88-2980-42ea-a8d3-3a630266934a)

# Docker

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

![image](https://github.com/user-attachments/assets/86e9cf1c-ae70-4188-be83-3adb576ae416)

# Key features of Docker-

 # 1.Containerization:
Applications run in isolated environments, which makes them portable and easy to manage.

# 2. Images and Dockerfile:
Docker uses images as blueprints for containers. A Dockerfile is a script that contains instructions to build an image.

# 3. Docker Hub:
A cloud-based registry where users can share and distribute Docker image.

# How Docker works:-

Docker works by providing a standard way to run your code. Docker is an operating system for containers. Similar to how a virtual machine virtualizes .containers virtualize the operating system of a server. Docker is installed on each server and provides simple commands you can use to build, start, or stop containers.

![image](https://github.com/user-attachments/assets/47366e98-d6f8-4b79-8e5e-25f13bfac89f)

# What is the structure of a Docker image?:-

A Docker image is composed of multiple layers stacked on top of each other. Each layer represents a specific modification to the file system (inside the container), such as adding a new file or modifying an existing one. Once a layer is created, it becomes immutable, meaning it can't be changed.

![image](https://github.com/user-attachments/assets/2d254a20-3046-4094-ae3e-4ce1497b33f4)

# HOW TO INSTALL DOCKER:-

To install Docker on a remote server using PuTTY, you'll first need to ensure you have access to a Linux server (like Ubuntu, CentOS, etc.) via SSH. Here's a step-by-step guide:

# Step 1:Connect to Your Server

# Step 2: Update Your Package Index

Before installing Docker, it’s a good idea to update the package index:

```
sudo apt update
```

# Step 3:Install Prerequisites

For Ubuntu, install the required packages:

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

For CentOS, run:

```
sudo yum install -y yum-utils
```
# Step 4: Add Docker’s Official GPG Key:

For Ubuntu:

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
For CentOS:

```
sudo rpm --import https://download.docker.com/linux/centos/gpg
```

# Step 5: Set Up the Stable Repository

For Ubuntu:

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
For CentOS:
```
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
# Step 6: Install Docker

For Ubuntu:

```
sudo apt update
```
```
sudo apt install docker-ce
```

For CentOS:
```
sudo yum install docker-ce
```

# Step 7: Start Docker

Enable and start the Docker service:

```
sudo systemctl start docker
```
```
sudo systemctl enable docker
```
# Step 8: Verify the Installation

Check if Docker is running:
```
sudo systemctl status docker
```
You can also run a test container:
```
sudo docker run hello-world
```
# Step 9: (Optional) Manage Docker as a Non-Root User
If you want to run Docker commands without sudo, add your user to the

Docker group:
```
sudo usermod -aG docker $USER
```
After running this command, log out and back in for the changes to take effect.
