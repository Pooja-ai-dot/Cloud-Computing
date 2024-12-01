# Cloud-Computing

Cloud computing is the delivery of computing services—including servers, storage, databases, networking, software, analytics, and intelligence—over the Internet ("the cloud"). This allows for faster innovation, flexible resources, and economies of scale.

# Docker

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

# Docker Components:-

Docker consists of several key components:

## 1.Dockerfile:
A text file that contains a set of instructions for building a Docker image.

## 2.Docker Image:
A template for creating Docker containers. It includes the application code, runtime, libraries, and settings.

## 3.Docker Container:
An instance of a Docker image that runs as an isolated process on the host system.

# How Docker Works:-

## Creating a Dockerfile:
Developers write a Dockerfile that specifies the base image and the steps to set up the application environment.

## Building a Docker Image:
The Dockerfile is used to build a Docker image, which contains all the necessary components to run the application.

## Running a Docker Container: 
The Docker image is used to create and run a Docker container. The container runs as an isolated process on the host system, sharing the host's OS kernel.

# What is the structure of a Docker image?

A Docker image is composed of multiple layers stacked on top of each other. Each layer represents a specific modification to the file system (inside the container), such as adding a new file or modifying an existing one. Once a layer is created, it becomes immutable, meaning it can't be changed.

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
# Conclusion
You’ve successfully installed Docker using PuTTY! If you have any questions or run into issues, feel free to ask.

# Container
A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

(in other and simple words )

Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), can handle more applications and require fewer VMs and Operating systems
# NGINX:
NGINX is a high-performance web server and reverse proxy server that is widely used for serving web applications, handling HTTP and HTTPS requests, and load balancing traffic. It is known for its speed, efficiency, and ability to handle a large number of concurrent connections with low resource usage.

# How to Install NGINX: 
In this tutorial, we’ll show you how to install NGINX on Linux.

# Open your Linux machine and run an update using the command below:
```
sudo apt-get update
```
Next, run this command:
```
sudo apt-get install nginx
```
# Then, enable your firewall with the following:
```
sudo ufw enable
```
# To verify NGINX is installed, run the following:
```
nginx -v
```
# You can run the command below to find out if NGINX is running:
```
sudo ufw status
```
After running this command, you should see the following:
status: active
# To check whether your NGINX server is working fine, run the following:
```
sudo systemctl status nginx
```
# using EC2 in aws:-
First open aws search EC2 then Launch Instance and there select keypair in putty then download it

after that Launch it and run putty and paste public id on HOST NAME and open that downloaded key pair for putty in SSH then Auth then Credentials and open there

# after that run it and write username as ubuntu as selected os and then type following commands
```
sudo apt update
```
```
sudo apt install apache2
```
# to install a web server on ip then 
```
sudo su
```
# for convert $ into # for getting admin role then 
```
cd /var/www/html/
```
## then 
```
ls
```
# for list of html file in it 
# then copy that html file name and write 
```
rm index.html
```
```
rm means remove command
```
```
vi index.html
```
# this will open a notepad like and write html code there like (vi is editor) -
# then press ctrl+c then shift+colon then write wq and enter
# now copy your public ip and paste it on browser you will see the texts written by you (by using html above)
# USING CONTAINER IN VM and adding nginx server by Docker:-
First open aws search EC2 then Launch Instance and there select keypair in putty then download it

after that edit network setting and click on add security group rule and select TCP,UDP,ALL TRAFFIC AND SELECT EVERYWHERE SOURCE TYPE IN THEM then Launch it and run putty and paste public id on HOST NAME and open that downloaded key pair for putty in SSH

(SSH (Secure Shell) is a way to securely connect to another computer over a network. It's like a safe tunnel that allows you to control a remote computer and transfer files to it, without anyone else being able to listen in or interfere with the connection.)

then Auth then Credentials and open there

after that run it and write username as ubuntu as selected os and then type following commands
```
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```
# this will install and run docker in your vm
```
newgrp docker
```
# this command will help us to use docker
```
docker ps
```
# this will list docker
```
docker --version
```
# this will display the version of docker installed
# now installing nginx
```
docker pull nginx
```
# You can download Nginx from a pre-built Docker image, with a default Nginx configuration, by above command. This downloads all the necessary components for the container.

```
docker run --name docker-nginx -p 80:80 nginx
```
# Nginx installed, you can configure the container so that it’s publicly accessible as a web server.
# run is the command to create a new container
# The --name flag is how you specify the name of the container. If left blank, a generated name like nostalgic_hopper will be assigned.
# -p specifies the port you are exposing in the format of -p local-machine-port:internal-container-port. In this case, you are mapping port :80 in the container to port :80 on the server.
# nginx is the name of the image on Docker Hub.
# now this will show this on your public ip
![image](https://github.com/user-attachments/assets/3580e366-05c9-4d1a-af59-92fbdcc171a8)
# In your terminal, enter CTRL+C to stop the container from running.
```
docker ps -a
```
# verify the container status with this command

```
docker rm docker-nginx
```
# Remove the existing container
```
docker run --name docker-nginx -p 80:80 -d nginx
```
# Create a new, detached Nginx container,By attaching the -d flag, you are running this container in the background.
```
docker ps
```
# this will obtain info about your container
```
docker stop docker-nginx
```
# Stop the container
```
docker rm docker-nginx
```
# remove the container
# Building a Web Page to Serve on Nginx
```
mkdir -p ~/docker-nginx/html
```
# Create a new directory for your website content within the home directory
```
cd ~/docker-nginx/html
```
# by this you navigate into this
```
vi index.html
```
# now press i and write your code in html like
![image](https://github.com/user-attachments/assets/074c0c86-15d1-49a5-90a8-14909e082d6a)
# then press ctrl+c then shift+colon then write wq and enter
```
docker run --name docker-nginx -p 80:80 -d -v ~/docker-nginx/html:/usr/share/nginx/html nginx
```
Linking the Container to the Local Filesystem
open your public ip in browser you will see as the content as your html code
# Using Your Own Nginx Configuration File
```
cd ~/docker-nginx
```
```
docker cp docker-nginx:/etc/nginx/conf.d/default.conf default.conf
```
# Copy the Nginx config directory into your project folder
```
docker stop docker-nginx
```
```
docker rm docker-nginx
```
# to rebuild the container stop the container then remove it
```
docker run --name docker-nginx -p 80:80 -v ~/docker-nginx/html:/usr/share/nginx/html -v ~/docker-nginx/default.conf:/etc/nginx/conf.d/default.conf -d nginx
```
# This command links the custom website pages to the container.
```
docker restart docker-nginx
```
# you need to restart your container to reflect changes on the associated pages.
# Orchestration:-
Cloud Orchestration can be defined as the coordination, arrangement, or end-to-end automation of the deployment of services in a cloud-based environment. It introduces and enforces a workflow for automated activities of various processes to deliver the desired service to its client. Cloud Orchestration tools take full use of IaaS services providers to reach out to fully automated deployment, deleting the manual processes which are considered time-consuming. Some Orchestration tools are Terraform, Ansible AWS Cloud Formation, etc.
![image](https://github.com/user-attachments/assets/ad9a2255-5dc3-4de2-9900-aff98ec26042)
# Kubernestes :-
ubernetes is an open-source Container Management tool that automates container deployment, container scaling, descaling, and container load balancing (also called a container orchestration tool). It is written in Golang and has a vast community because it was first developed by Google and later donated to CNCF (Cloud Native Computing Foundation). Kubernetes can group ‘n’ number of containers into one logical unit for managing and deploying them easily. It works brilliantly with all cloud vendors i.e. public, hybrid, and on-premises. 
![image](https://github.com/user-attachments/assets/a19dfd18-41dd-4a99-b684-6ff19b990b0a)
# Pods:
Containers are grouped into pods. A pod is the smallest unit in Kubernetes and can have one or more containers that share the same resources.
# Minikube:-
Minikube is a one-node Kubernetes cluster where master processes and work processes both run on one node. Minikube is local Kubernetes, focusing on making it easy to learn and develop for Kubernetes. A prerequisite to use Minikube is a Docker container or a Virtual Machine environment. Minikube provides you a way to easily deploy application on Kubernetes for learning and developing purposes even if you don't have enough resources like memory, CPU etc.
# USING MINIKUBE IN AWS
## First open aws search EC2 ,and download your passkey then Launch Instance and select 22.04 AMI then select t2.xlarge instance type then select keypair then configure storage to 30 GB then enable all traffic in network and Launch.

## Launch PuTTY and add the IP address from instance and add key pair file and open the PuTTY terminal.

## Now connect it with putty and login into it by writing ubuntu
## now put some commands
```
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```
## it will install docker
```
sudo usermod -aG docker $USER
```
```
newgrp docker
```
## it will Add your local user to docker group so that your local user run docker commands
```
sudo snap install kubectl --classic
```
## it will intall kubernetes
```
kubectl version --client
```
## it checks the version
# Installing Minikube
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
```
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
```
minikube version
```
## it checks its version
## Starting Minikube with Docker Driver
```
minikube start --driver=docker
```
## if you encounter root privileges error, run:
```
minikube start --driver=docker --force
```
```
minikube status
```
## it checks its status
```
kubectl cluster-info
```
## it checks cluster info
```
kubectl config view
```
## it will show the config
```
kubectl get nodes
```
## it will display nodes in it
```
kubectl get pods
```
## it will show pods in it

```
kubectl create deployment nginx-web --image=nginx
```
```
kubectl expose deployment nginx-web --type NodePort --port=80
```
kubectl get deployment,pod,svc

## it will deploy a sample nginx deployment
```
minikube addons list
```
```
It will display all addons
```
```
minikube addons enable dashboard
```
```
minikube addons enable ingress
```
## this enables these addons
```
minikube dashboard --url**
```
## it will get the url and run the dashboard of MiniKube

```
kubectl proxy --address='0.0.0.0' --disable-filter=true &
```
## This will enable port :8001 to access it on your public ip
```
http://server_ip:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/workloads?namespace=default
```
## in browser replace server ip with public ip
## Now go to above link and replace server_ip with your public ip and it will show you like :

![image](https://github.com/user-attachments/assets/320fca56-300c-46a1-ac01-5bfff8604dcc)
# KVM:- Kernel-based Virtual Machine
Kernel-based Virtual Machine (KVM) is a software feature that you can install on physical Linux machines to create virtual machines. A virtual machine is a software application that acts as an independent computer within another physical computer. It shares resources like CPU cycles, network bandwidth, and memory with the physical machine.
KVM is a Linux operating system component that provides native support for virtual machines on Linux.
## how does kvm work ?
Kernel-based Virtual Machine (KVM) requires a Linux kernel installation on a computer powered by a CPU that supports virtualization extensions. Specifically, KVM supports all x86 CPUs, a family of computer chips capable of processing the Intel x86 instruction language. 

![image](https://github.com/user-attachments/assets/f67ba06c-1458-478e-a582-a69bf92e21e8)

# Openstack:-
OpenStack is an open-source platform that lets you create and manage cloud computing services. It allows users to control computing power, storage, and networking in a data center through a web interface. Essentially, it helps organizations build their own private or public clouds, making it easier to deploy and manage applications.

![image](https://github.com/user-attachments/assets/2be70f8c-9490-4ae7-a995-4a25fbdaa8d7)
# QEMU 
QEMU is an open-source emulator and virtualization tool that allows you to run different operating systems on a host machine.

![image](https://github.com/user-attachments/assets/55ff0762-9e16-4f85-834f-78e4b4605b0b)
# VPC
Amazon Virtual Private Cloud (VPC) is a virtual network that allows users to launch AWS resources in a logically isolated environment. It's a foundational service of AWS that gives users complete control over their virtual networking environment.

## What is the difference between EC2 and VPC?
•EC2 is a virtual server that you can run your software on. VPC is a virtual network that you use to connect your virtual servers, and other resources.

## Go to VPC and create a VPC then we have to create 4 subnets , where 2 subnets are private and other two are public .

![image](https://github.com/user-attachments/assets/2c7ac4b4-fe3e-4794-99aa-9b7e0ee691a0)

![image](https://github.com/user-attachments/assets/27f43199-1105-4d4c-8608-3264145470dc)
## create gateways:-
1st create INTERNET GATWAY , whic is to be connected to your VPC which is created earliy.

![image](https://github.com/user-attachments/assets/c220404f-9f8d-4d62-99a8-67c64bcfb07d)
•2nd we have to create VPG virtual privaye gate, and connect to VPC .
## create route tables
•Now we have to go to the route table and create 2 route table , one for IGW and another for VGW .

![image](https://github.com/user-attachments/assets/85f766e9-7e85-4cc0-8a78-85821ce84688)
•Now we have to connect two public subnet in myigw and on other we have to add the private subnets .

![image](https://github.com/user-attachments/assets/817a35b1-26fb-4580-a730-df4e712923aa)
## create instances
• now we have to create two instnaces where we have to enable the public IPv4 .

•then on both instance we have to downlaod the web server here i have downlaoded the apache2 server

-- after that i chech that my instances are working or not .

![image](https://github.com/user-attachments/assets/84fdc358-4f26-4525-8e1f-349f6b408a0f)
## now we have to create the load balancer
--where we have to give vpc, aviablity zone of the ec2 instance

•then we have to create the target group where we have to select the two insatance we have create then we have to go to helath check edited option which was present below the load balancer is create ,then edit it as given below image

![image](https://github.com/user-attachments/assets/766e865a-29d8-4aa5-8e73-1aca01e9c56d)
•after that come to load balancer where we have to select the target group which we have created then make the load balancer , it will look like the given image below .

![image](https://github.com/user-attachments/assets/5182419e-3b46-463d-aab8-e9a5317f52e3)

![image](https://github.com/user-attachments/assets/2872a4eb-8764-45f5-9422-45e86f05b547)
now put on any one instance write following commands in putty -
```
htop
```
```
seq 999999999999999999999999999999999999999999999999999999999 > /dev/null &
```
```
htop
```
## book link for reference of VPC given below (page 55 )
{ https://www.scribd.com/document/454176546/AWS-lab-practice-guide-by-www-server-computer-com-v1 }
# NETWORKING

![image](https://github.com/user-attachments/assets/ce48d171-a584-495b-8854-0a098747e4b4)
## what is client and server

![image](https://github.com/user-attachments/assets/7d040173-1c58-4e40-ab91-9ad8932b51c7)
## types of network

![image](https://github.com/user-attachments/assets/1f62b0ed-23c0-445a-bdec-23a8d7a4b4ee)
# Network Devices:-
## 1. network adaptor/ interface
• connects a device to network.

• has a Mac address by manufacturer

• second layer device

## 2. switch
•it is a very multiport network bridge that uses MAC address to forward data

•link layer device

## 3. Router
•it is a device that forwards data between computer networks

• 3rd layer device

## 4. HUB
•network device that used to connect multiple computers in a network

• all information send to the hub is automatically send to each port to every device

## 5. TAP
(WORKS ON LAYER 2 -- ethernet frame )

used to create a user space network bridge.

## 6. TUN
( WORKS ON LAYER 3 -- IP packets )

create a tunnel network to reach another network .

# Basic terms for understanding networking better:-
## 1.NAT :-
it is a process in which one or more local IP addresses are translated into one or more global IP addresses and vice versa

## 2. veth :-
these are pair of virtual network interfaces that are used to connect network namespaces together.

## 3.DPDK :- Data Plane Development Kit
it is a set of libraries and drivers that accelerates packet processing and their ability to create packet forwarders without the need of costly custom switches and routers

## 4. NIC :- network interface card
It allows one device to connect to network

## 5. DPU :- Data Processing Unit
it is a new programmable processor that helps move data around data centres. it ensures right data goes to right place in right format quickly .
## 6.CSI :- Container Storage Interface
## 7. OVS :- Open virtual switch
it is used with hypervisors to interconnect virtual machines within a host and between different hosts accross networks.

## 8. QEMU :- Quick emulator
free open source machine it can run various guest operating systems (OS's ) and architecture on a single host system.

## 9. Docker :-
it is like a container that holds everything your application needs to run including the code, libraries.
## 10. Kubernets :-
it is like a manager for containers .it helps to deploy, scale and manage a group of containers making sure they run smoothly.
## 11. web assembly:- (WASM)
technology that allows you to run code written in different programming languages. It is a way to build high speed, responsive web applications that can handle data and communicate over networks.

## 12. Firewall :-
security system that controls incoming and outgoing network traffic based on pre- determined security rules.

## 13. DMZ :-
The DMZ design and architecture involve several elements including the firewalls, routers, and servers. The key objective is to ensure that access to the internal network is tightly controlled while offering services to the outside world through servers in the DMZ.
## 14. VxLAN :-
It is tunneling report that tunnel Ethernet traffic (layer 2) over an IP network(layer 3).

### 14.1 VTEP:-
it is a device that's responsible for encapsulating and de-capsulating layer 2 traffic.

## 15. LINUX Bridge :-
it is a kernel module that behaves like a network switch .It is usually used for forwarding packages on routes or gateways or between virtual machines.

## 16. Pktgen :-
it is a tool for high speed package generation and testing. It in the Linux kernel.

netns :- network namespace
feature of Linux kernel that provides a way to create isolated network environment.

TAP is often used to connect VM or containers to a physical network

# KVM :- kernel virtual machine
( typer 1 hypervisor)

# CNI :- Container Networking Bridge
it is responsible for setting up the network ( assigning IP address, create network bridge) for containers ,enabling communication between containers and outside world

examples VLAN , IPvLAN , CALICO , FLANNEL , VMware. etc

## Flannel :-
it acts as a layer that allows containers to send and receive data seamlessly accross various hosts .

## working:-
it runs a small single binary agent on every host. this networking tool gives every host an IP subnet.

# Packet Switching:-
when we send email or web page the data does not travel as single continuous stream instead is broken down into smaller chunks called packets .
# key functions of network core :-
## 1. Forwarding :-
• it is a local action of moving and arriving packets from a router's input to appropriate router output link.
## 2. Routing :-
• global process of determining the full paths packets take from source to destination
## Network Protocols:-
set of rules that determine how the packet is to be transferred and received and in which format .
## 1. TCP
it ensures reliable order delivery of data between applications . It handles things like breaking data into packets

## 2. IP
responsible for addressing and routing packets across the internet.
## 3. HTTP
it is a protocol that powers the world wide web defining how messages are formatted and transmitted between web browsers and servers.
# NETWORK STACK

![image](https://github.com/user-attachments/assets/63a4d659-eb2d-4912-9d64-3cd1dc2e4868)
## TCP /IP
provide reliable transmission of data.

## UDP
provides faster but less reliable transmission of data.
## Packet flow, also known as network flow or traffic flow:-
it is the sequence of packets that travel from a source computer to a destination.

•Packets are segments of data that are routed through a network of interconnected devices, such as switches and routers, before reaching their destination.

--below images shows network setup for packet flow

![image](https://github.com/user-attachments/assets/c8d8598d-12e4-4a29-8971-443d573c69f6)

![image](https://github.com/user-attachments/assets/5c9950f5-f8c2-4d99-8015-442fec9dda39)

![image](https://github.com/user-attachments/assets/c25f6591-827b-461c-8369-f23d33271d43)
# Explanation:-
user1 wants to send data user2 does the data is broken down into packets. user1 don't know the MAC address user2 but it show the Mac address of the gateway. show the packets are put it into frame which have MAC address of the router.
