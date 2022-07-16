# Port Mapping in Docker
- Go to Docker file and write this line 
- `EXPOSE 3000`
- 3000 is a port number

### Docker Image build
```
sudo docker image build -t my-node-app .
```
### `Run Container with Port Mapping`
```
sudo docker container run -d -p 3000:3000 --name c_node my-node-img
```
**`-d`** => Container run in background <br>
**`--name`** => set Container name like c_node <br>
**`-p`** => use for port mapping <br>
**`3000:3000`** => first 3000 is `local` port address and `second` 3000 is `docker` port address, so local port mapping the `docker` port
