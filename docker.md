## <center> 🐳 <font color="red" >docker </font> 🐳</center>  
---

[DOCKER cheatsheet](https://dockerlabs.collabnix.com/docker/cheatsheet/)

# container is a running instance of the image
* node ubuntu python etc.. are the images on the basis of requirement lots of images come together making docker image
so docker images is combination of many images or and also base image that is the os.

### What is docker
* A project require different packages let say we are working on a project for a years initially when we started project it was node-16
react-16 postgress-4 express-3 
* we hire a new developer when he pulled our code from github he installed all the dependecies like he will install the node-18 react-19 postgress-6 express-4 because this are the latest this will cause a lot of error as many of the code that was written previously got deprecated
* Also sometimes due to different configuration that code will not run

## Code is running on my machine but not others
To handle this problem docker arive 

#### Docker is a Light Weight Portable Virtual Machine 

| Feature                | Docker                                      | Virtual Machines                             |
|------------------------|---------------------------------------------|----------------------------------------------|
| **Underlying Technology** | Runs on WSL (Windows Subsystem for Linux) or natively on Linux/macOS | Runs on a hypervisor (Type-1 or Type-2)      |
| **Kernel**             | Shares the host OS kernel                   | Runs a separate OS with its own kernel       |
| **Startup Time**       | Fast                                        | Slower due to full OS boot                   |
| **Resource Usage**     | Lightweight, uses fewer resources           | Heavier, uses more resources                 |
| **Isolation**          | Process-level isolation                     | Stronger isolation with separate OS instances|
| **Portability**        | Highly portable across different environments | Portable but larger and more cumbersome      |
| **Use Cases**          | Microservices, CI/CD pipelines, quick startup | Running multiple OS environments, strong isolation |
| **Management**         | Managed using Docker CLI and Docker Compose | Managed using hypervisor management tools    |


##### We can pull the whole docker container that is itself a lightweight virtual machine and run it on our machine locally without any further need to install the dependencies also we can push the whole docker again that is lightweight virtual machine on docker hub 

## Analogy of GitHub and DockerHub

1. DockerHub hosts many container images.
2. GitHub hosts many code repositories.
3. GitHub is used for version control and code management.
4. DockerHub is used for storing and distributing container images.

 **GitHub**: Primarily used for version control and collaboration on code. It hosts repositories containing source code, documentation, and other related files.
 
**DockerHub**: Used for storing and distributing container images. These images contain the application and its dependencies, but not the entire machine. They package the software in a way that it can run consistently across different environments.

## Difference between image and container

* Images are like the Classes that is the blue print
where containers are like Object or instance of it
* lets take another example let say we have GTA-5  its only a game or app like docker image but when we run it its the real thing that came out of code like container 
The game itself (GTA-5) is like the Docker image, containing all the necessary files and configurations. When you run the game, it becomes an active, interactive experience, similar to how a container is a running instance of the image.
