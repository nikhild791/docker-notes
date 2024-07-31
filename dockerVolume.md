## <center><font color="red">🐳 Docker Volume 🐳</font></center>
---
Docker container gets a temperary memory if we make a database inside the container and write it when the container gets deleted the database and the data also get deleted
##### docker volumes are a kind of permanent storage which you can bind with your container making it a permanent storage for your container

### Let's mount a local directory to a container
* make a app folder with index.js file having the following code
``` console.log("Hello World from nikhil")```
* open terminal pull a node image
```
docker run -it node:latest
docker container ls -a  ## a stands for all
```
* Let's moun the app folder to node container
```docker run -it -v [Location of app]:/home/app node bash```
If you are in windows use this command
```docker run -it -v %cd%/dockerVolume:/home/app node bash```
cd = current directory for windows like pwd cwd
%cd% it will treated as variable
A bash will open do 

```
uname whoami ls [separately]
To see the code inside the index.js
cat index.js
```
* Let's install the nodemon to check whether the folder is mounted properly or not and also syncing with the container or not
```
npm i -g nodemon
nodemon index.js
```
now make changes in index.js it should reflect in the node container

## Create and remove a volume 
```
docker volume create data
docker volume ls
docker volume rm data 
```
## Mounting volume to container[data volume to node container]
```docker run -it -v data:/data node bash```
let's make a directory inside the volume
```
cd data
mkdir nikhil-dubey
```
## Lets check whether the directory is made or not
open new terminal and mount volume data to ubuntu image
```docker run -it -v data:/myapp ubuntu bash```
* The data directory is mounted to myapp folder go inside it
* do ls you will see the nikhil-dubey folder
* make a new directory nikhild
* Go inside the node container you will see the nikhild inside the data folder
