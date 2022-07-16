# **`Make Node Image`**

 - Create Docker file `Dockerfile` in node app directory
 - Open `Dockerfile` and write some instruction.
 
 ```
1 FROM node:16-alpine
2 WORKDIR /NODES
3 COPY . .
4 RUN npm install
5 CMD [ "npm","run","dev" ]
or 
5 ENTRYPOINT [ "npm","run","dev" ]
 ```
 ### **`line 1 :FROM ndoe:16-alpine`**
 **node** => baseImage for node app \
 **16** => node version \
 **alpine** =>  Linux Flawer , `Alpine` size low other Linux Flawer

 ### **`line 2:WORKDIR /NODES`**
 **WORKDIR** => Working Directory

 ### **`line 3 :COPY . .`**
 COPY Source Destination \
 **Source**=> Represent node_app working Directory \
 **Destination** => Represent Docker Container working Directory \
  
  - If you wand to ingnore fole or directory, not copy in Docker container write `dockerignore` file \
  like : node_modules/ directory

 ### **`line 4: RUN npm install`**
**npm install** => install node packege modules \
**RUN** => `RUN` command use for bild. You can ruse many `RUN` command in `Dockerfile`. \
**`line 5 : CMD ["npm","run","dev"]`**

**CMD** => Command use for run node server. `CMD` command user end of file. `CMD` command used to run app. `CMD` use only one time in file.

**`line 5 : ENTRYPOINT ["npm","run","dev"`**
**ENTRYPOINT** => `ENTRYPOINT` and `CMD` are same.

 <br>
 <br>

# **`Open new terminal create image build`**

### **`Build Docker Image`**
```
sudo docker image build -t my-node-app .
```
**`-t`** =>  use for tag -> my-mode-app .set tag name for docker image <br> like : my-node-app<br>
 **`.`** => Dot represent dockerfile location <br>

### **`View Docker Images`**
```
sudo docker images
```
or
```
sudo docker image ls
```
 # **`Create new Container and run Docker image`**
 ### `Run image in Container`
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

