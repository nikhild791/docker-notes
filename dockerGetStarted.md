
### Commands to run docker
some basic commands might not run windows
```
docker --version
whoami
uanme
```

### To list all the docker containers
```docker container ls```
### To stop docker
```docker stop dockerId ```
### To remove the docker container
```docker container rm dockerId```
### To remove the docker container forcefully
```docker container rm -f dockerId```

### To list all the docker images
```docker image ls or docker image```
### To remove the docker image
```docker image rm imageId ```

### To run ubuntu on docker please remind docker is aslo a kind of virtual machine
```docker run -it ubuntu```
**-it** === **interactive** gonna interact with the ubuntu machine
```docker run -d ubuntu``` 
**-d** == **deatached mode** 

### If only want to pull the image not want to use it
```docker pull node```
#### now we can interact with the node image 
```docker run -it node```
#### To rename the dockerfile
```docker tag nikhil791/myapp nikhil791/rename ```

### Lets make a simple docker image
1. make a simpel node server
```
npm init -y
npm i express
```
2. make a simple express app
```
const express = require('express')
const app = express()
const port = 9000

app.get('/', (req, res) => {
  res.json(message:'I am inside docker container')
})

app.listen(port, () => {
  console.log(`Server is running on port ${port}`)
})
```
3. In order to make a docker image make a docker file naming "Dockerfile"
```
FROM node:latest

COPY index.js /home/app/index.js
COPY package.json /home/app/package.json

WORKDIR /home/app

RUN npm install

EXPOSE 9000

CMD [ "node", "index" ]
```
### To build images
```docker build -t myapp . or the file location```
### again to run docker
```docker run -it myapp``` 
### To check whether the container is running status
```docker ps```
but it will not work as you have exposed the 9000 port inside the docker machine and also you have exposed that port to the external world but have not mapped it to main machine
### Mapping the port or Port mapping p stand for port
```docker run -p 3000:9000 myapp```
* here if we don't write the EXPOSE 9000 in the Dockerfile the servers 9000 port will be still accessible because of the run -p command
### if want to use the machine with running
```docker run -it -p 3000:9000 myapp```

##### if there are to many file there you are not going to copy all of them one by one
```
COPY index.js /home/app/index.js
COPY package.json /home/app/package.json
instead of this use
COPY . /home/app
it will copy all the file also the node modules to avoid this
```
make a **.dockerignore** file and add
node_modules/

## Pushing images on dockerhub
```docker build -t username/image_name . or the file location```
* it is the naming convention and every idiot should follow it
```docker push username/image_name```

```app.run(debug=True,host="0.0.0.0", port=5000) ```
####  with host we can access this app from any device from same network 
```app.run(debug=True, port=5000)``` 

#### it will only bind to localhost so the server will not accessble from the outside whether you exposet the 5000 port or not