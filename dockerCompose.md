## <center><font color="red">🐳 Docker Volume 🐳</font></center>

#### In order to run multiple container who are connected to each other use docker compose 

* make **docker-compose.yml**
see format online

##### To set up the compose  and start running
```docker compose up```
```docker compose up -d``` up in deattached mode in background

#### To down the all container
```docker compose down```

##### To check a compose file 
[docker-compose.yml](https://github.com/calcom/cal.com/blob/main/packages/prisma/docker-compose.yml)

##### To delete all unused images
```docker rmi $(docker images -aq or docker images -a -q) // if you try to remove the running images it will throw error first stop or remove the running container than run the command```
