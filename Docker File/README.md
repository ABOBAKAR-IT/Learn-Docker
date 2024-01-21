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