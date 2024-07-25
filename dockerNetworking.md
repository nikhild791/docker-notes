## <center><font color="red">🐳 Docker Networking 🐳</font></center>
---
* same as the virtual machine networking here are seven types of network present
1. bridge - laptop ke andar ek local address use karega like laptop is router for it
2. host - laptop  ka ip use karega
3. macvlan - make a separate machine direct router se connect hoga making it more usefull for hacking it will have it's own macaddress
4. ipvlan - more control over ip address assign ip to daemon according to given ip poll
5. overlay -- multiple daemon ko sath me lata hai
6. none - isolate the machine 

### Docker uses default bridge network

### find a repo that has network tool install init i'd find one might not run when you see
```docker run -it --name server1 weibeld/ubuntu-networking```
#### To check whether the server1 is connect to internet or not 
```ping google.com```

### Some networking command
```
ipconfig for windows for linux/mac ifconfig
docker network ls
docker inspect bridge
```


### Let's ping two dockers
* create another ubuntu container
```docker run -it --name server2 weibeld/ubuntu-networking```
* To know ip address use 
```
hostname -I
ping [ipaddress]
```

### the above will be on the same class of the network

## Lets create a network
```
docker network
dokcer network ls
docker network create work 
```
###### work is default bridge type network but will be of different class have different ip address

### Creating a container with the network type of bridge
```docker run -it --network work --name server3 weibeld/ubuntu-networking```
```hostname -I```
both server 1[172.17.0.2] and server 3 has different ip like[172.18.0.2]

since the server1 and server3 are on the different class of network or on the different bridge you cannot ping to one another 
* we can not ping a container by it's name because they are on the default network 

### Let's assign work network to server1
```docker network connect work server1```
now server1 will have 2 ip address and connected to default bridge as well as our work network
#### Lets ping server1 to server3
ping server1 or it's work ip address
```
docker start server3
docker exec -it server3 bash
```

so our docker is connect through a bridge to our machine so when we want to run any web application on the specific port like 3000 we have to do port-forwarding so that our machine can access the daemon's port

## connecting our daemon to host
```docker run -it --network host server2``` 

