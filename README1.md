# Docker

Docker is an open container management platform. It is a software platform for developing, shipping, and running applications based on containers — small and lightweight execution environments that make shared use of the operating system kernel and run it in isolation from one another. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. 
# VMs vs Containers
## What is a Virtual Machine?
Virtual Machine is a system which acts exactly like a computer. VMs are like physical hardware turning one server into many servers. It uses technology called hypervisor which allows multiple VMs to run on a single machine. Each VM has a full copy of an operating system, the application, necessary binaries and libraries. VMs are bulky in nature.<br>
<br>
<img src="./src/vm_pic">
They have a full OS with its own memory management installed with the associated overhead of virtual device drivers. In a virtual machine, valuable resources are emulated for the guest OS and hypervisor, which makes it possible to run many instances of one or more operating systems in parallel on a single machine (or host). Every guest OS runs as an individual entity from the host system. Hence, we can look at it an independent full-fledge house where we don’t share any resources.



## What are Containers?
Due to the large number of libraries, packages, dependencies and other software components required for an application to run, it is one of the major issues of modern software development to operate and maintain these heavy applications in a cluster isolated from one another without interfering with each other’s operations. One solution to this problem is virtual machines, which keep applications on the same hardware entirely separate, and reduce conflicts among software components but virtual machines are bulky as it requires its own OS making it difficult to maintain and upgrade.

<br><br>
<img src="./src/docker_pic">


Unlike this, Containers isolate application environments from one another, and only share the underlying OS kernel. Containers are an abstraction at the app layer that packages code and dependencies together. By default, a container is relatively well isolated from other containers and its host machine. You can control how isolated a container’s network, storage, or other underlying subsystems are from other containers or from the host machine. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), can handle more applications and require fewer VMs and Operating systems.

# The following are the significant differences between Docker and VMs.
`OS and Architecture:-` Virtual machines have a host OS and the guest OS inside each VM. Guest OS can be any OS, like Linux or Windows, irrespective of host OS. While Docker containers host on a single physical server with a host OS, which shares among them. As it shares the host OS between containers it makes them light and increases the boot time.<br>
`Portability:-`
  Virtual machines are isolated from their OS, and so, they cannot be ported across multiple platforms. Docker containers can be easily ported across different platforms as they are self-contained and can run applications in any environment, and since they don’t need a guest OS. <br>
`Performance:-` Virtual machines are more bulkier than Docker containers as the virtual machines need to load the entire OS to start. The lightweight architecture of Docker containers are light weight as they don’t have a guest OS.

# What is Docker?
Docker is an open-source platform that makes it easy to create containers and container-based apps. To understand how Docker works, let’s take a look at its architecture and some of the components you would use to create Docker-containerized applications.
<br>
Docker is written in the Go language. It uses a technology called namespaces to provide the isolated workspace called the container. When you run a container, Docker creates a set of namespaces for that container. These namespaces provide a layer of isolation. Each container runs in a separate namespace and its access is limited to that namespace.



# Docker architecture
Docker uses a client-server architecture. The Docker client communicates with the Docker daemon, which is responsible for building, running, and distributing your Docker containers. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.

<img src="./src/data1">
<img src="./src/data2">

# Docker Architecture Overview
Now that you've become familiar with most of the fundamental concepts regarding containerization and Docker, it's time for you to understand how Docker as a software was designed.

The engine consists of three major components:

`Docker Daemon:` The daemon (dockerd) is a process that keeps running in the background and waits for commands from the client. The daemon is capable of managing various Docker objects.<br>
`Docker Client:` The client  (docker) is a command-line interface program mostly responsible for transporting commands issued by users.<br>
`REST API:` The REST API acts as a bridge between the daemon and the client. Any command issued using the client passes through the API to finally reach the daemon.




# Docker Components
Images
An image is a read-only template with instructions for creating a Docker container. For example, you can build an image which is based on the ubuntu image, and install the Apache web server and your application, as well as the configuration details needed to make your application run.
<br>
You can create your own images and publish them in a registry. To build your own image, you create a Dockerfile with a simple syntax for defining the steps needed to create the image and run it. Each instruction in a Dockerfile creates a layer in the image. When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuilt. This makes images lightweight, small, and fast, as compared to other virtualization technologies.



# Containers
A container is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. It is isolated from other containers and its host machine. When a container is removed, any changes made to its state that are not stored in persistent volumes will also get removed.

# Docker registries
A Docker registry stores Docker images. Docker Hub is a public registry that anyone can use, and by default Docker looks for images on Docker Hub. You can even run your own private registry. When you use the docker pull or docker run commands, the required images are pulled from your configured registry. When you use the docker push command, your image is pushed to your configured registry.