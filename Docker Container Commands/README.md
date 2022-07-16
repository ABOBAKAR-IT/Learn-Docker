# **`Docker Container Commands`**
 ### `Create new container Run image in Container`
 ```
 sudo docker container run  my-node-img
 ```
 ### `Display running Container`
 ```
 sudo docker container ls
 ```
 ### `Display All Running and stop Container`
 ```
 sudo docker container ls -a
 ```
 ### `Start existing  Container`
 ```
 sudo docker container start CONTAINER_ID
 ```

 ### `Go to node app file in Docker`
```
sudo docker exec -it CONTAINER_ID sh
```
### `Stop Docker Container`
```
sudo docker container stop CONTAINER_ID
```
or
 ```
sudo docker container kill CONTAINER_ID
```
or
```
sudo docker container kill CONTAINER_NAME
```
### `Create new Container with container name and run img with background`
```
sudo docker container run -d --name c_node my-node-img
```
**`-d`** => Container run in background <br>
**`--name`** => set Container name like c_node

### `Check Container log`
```
sudo docker log CONTAINER_ID
```
or
```
sudo docker log CONTAINER_NAME
```
or
```
sudo docker log CONTAINER_NAME -n 2
```
**`-n`** => show last 2 logs

### `Remove all stop container`
```
sudo docker container prune
```
### `Remove  container`
```
sudo docker container rm CONTAINER_ID
```
OR
```
sudo docker container rm CONTAINER_NAME
```
### `Remove all running and stop container and images`
```
sudo docker system prune -a
```
### ` Go to inside docker container`
```
sudo docker run -it CONTAINER_NAME sh
```
