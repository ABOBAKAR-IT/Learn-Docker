# Docker Volume

Docker Volume is a feature provided by Docker that allows you to manage persistent data in Docker containers.
When a container is created and started, it generally  runs in an isolated environment with its own file system.
However any data stored within the container is typically non-persistent, meaning it will be lost when the container is stopped or removed.
Docker Volumes provide a way to overcome this limitation by allowing you to create a separate storage area that can be shared between containers or between a container and the host system.
Volumes provide a mechanism for storing and managing data separately from the container itself, ensuring that the data persists even if the container is stopped or deleted.




## Create Volume
```bash
docker volume create my-vol
```
## List Volume
```bash

docker volume ls
```
## Inspect Volume, check Volume Detail
```bash    
docker volume inspect my-vol
```    
## Remove Volume
```bash
docker volume rm my-vol
```
## Remove all Volumes
```bash
docker volume prune
```

## Link Volume when run container 
```bash
docker run -d -v my-vol:/mydata --name mycontainer nginx
```
`/mydata` this is Container Directory


## Read Only Volume Link
```bash
docker run -d -v my-vol:/mydata:ro --name mycontainer nginx
```
`ro` use for Read Only.