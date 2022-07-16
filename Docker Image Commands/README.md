# `Docker Image Commands`
### **`Build Docker Image`**
```
sudo docker image build -t my-node-app .
```
**`-t`** =>  use for tag -> my-mode-app .set tag name for docker image <br> like : my-node-app<br>
 **`.`** => Dot represent dockerfile location <br>
### **`Build and Tag the Image`**
```
sudo docker image build -t my-node-app:1.0.0 .
```
**`-t`** =>  use for tag -> my-mode-app .set tag name for docker image <br> like : my-node-app<br>
 **`.`** => Dot represent dockerfile location <br>
 **`my-node-app`** => image name <br>
 **`:1.0.0`** => image version <br>
### **`View Docker Images`**
```
sudo docker images
```
or
```
sudo docker image ls
```
### `Remove all unused images who not referenced by a container`
```
sudo docker image prune 
```
**prune** => use to delete dangling images

### ` Go to inside docker image`
```
sudo docker run -it IMAGE_NAME sh
```

