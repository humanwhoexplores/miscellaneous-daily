### 1.) How to Run a docker container 
docker run -ti ubuntu:latest bash

# -ti means terminal interactive 

### 2.) Show docker containers
docker ps -l // last running docker container 
docker ps -a // all containers

### 3.) If you want to run a command inside a running docker container 
docker exec -it <container-id> bash

### 4.)  To make an image from a container
docker commit <container-id>
This outputs a SHA 

We can use the image to run a new container 

docker run -ti <SHA> bash

### 5.) Delelte Container via
docker rm <container-id or container-name>

Delte the container once it runs the bash script 
docker run --rm -ti ubuntu:latest bash -c "sleep 5 ; echo done"

### 6.) running in detached mode 
docker run -d ubuntu:latest 

