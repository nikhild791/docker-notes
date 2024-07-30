## <center><font color="red">🐳 Docker Volume 🐳</font></center>

### To run the container in the background 
```docker run -d -p 8080:80 nginx```

### To see all the container jinhe chala chala ke band kar diya hai 
```docker ps -a```

### once you entered inside the container you can allow any port
```ufw allow 5000```

### remove container using 
```docker rm containerId```

### remove aaltu faltu bekar sada hua container and images using
```docker system pruve``` 

### To stop a running container
```docker rm -f containerId```

### To open bash of the running container
```docker exec -it containerId bash```

### To copy docker files to machine or from machine to docker
```docker cp <source> <destination>```

### To commit all the changes of container and make a image of it
```docker commit containerId``` without name
```docker commit containerId harry/nginx:6.7``` harry/nginx will it's repo name 6.7 will it's tag


