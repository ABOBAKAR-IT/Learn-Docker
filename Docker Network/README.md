# Docker Network
Docker networking is a fundamental aspect of Docker that enables communication between Docker containers and external networks. It allows you to connect containers together, as sell as connect containers to the host machine and other external resources.
A container has no information about what kind of network it's attached to , or whether their peers are also Docker workloads or not.
A container only sees a network interface with an IP address, a gateway, atouting table, DNS services, and other networking details.
By Default,when you create or run a container using docker create or docker run, the container doesn't expose any of its ports ot the outside world.
Use the --publish or -p flag to make a port available to services of Docker .
This creates a firewall rule in the host, mapping a container port to a port on the Docker host to the outside world.

# Docker Network Driver

 - `Bridge` The default bridge network is good far funning containers that don't require special networking capabilities. User-defined bridge networks enable containers on the same Docker host to communicate with each other. A user-defined network typically defined an isolated network for multiple containers belonging to a common project or component.


 - `host` Host network shares the host's network with the container. When you use this driver, the container's network isn't isolated from the host.

 - `overlay` Overlay networks are best when you need containers running on different Docker hosts to communicate, or when multiple applications work together using Swarm services.

 - `macvlan` Macvlan networks are best when you are migrating from a VM setup or need your containers to look like physical hosts on your network, each with a unique MAC Address

 - `ipvlan` IPvlan is similar to Macvlan, but doesn't assign unique MAC addresses to containers. Consider using IPvlan when there's a restriction on the number of MAC addresses that can be assigned to a network interface or port.

 - `none` No Networking


## List all Network
```bash
docker network ls
```
## inspect bridge network
```bash
docker network inspect NETWORK_NAME
```
## Create Network   

```bash
docker network create mynetwork
```
## Create user define bridge Network   
```bash
docker network create --driver bridge my-network
 ```

## Connect network when Container run
```bash
docker run -d --name my-container --network my-network my-image
```

## Connect specific network with existing running container
```bash
docker network connect my-container my-network
```
## Disconnect a running container to an existing user define network bridge
```bash
docker network disconnect my-container my-network
```

## Remove Network
```bash    
docker network rm my-network
```    