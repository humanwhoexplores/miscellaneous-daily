##### Resources
https://www.tutorialworks.com/why-containers-stop/#:~:text=You're%20running%20a%20shell,t%20attached%20an%20interactive%20terminal.

#####


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

### 7.) Stopping a container V/S removing a container
docker kill <container id / name> : stops the container
docker rm <container id / name > : removes the container

Q.) Why all containers are showing exited : 
╭─krchopra@krchopra-Mac ~/Workbook/miscellaneous-daily ‹master› 
╰─$ docker ps -a            
CONTAINER ID   IMAGE           COMMAND       CREATED          STATUS                      PORTS     NAMES
9ee2b4d6eb6a   fedora:latest   "/bin/bash"   14 seconds ago   Exited (0) 13 seconds ago             exciting_boyd
646371d5df56   ubuntu:latest   "bash"        55 seconds ago   Exited (0) 54 seconds ago             agitated_lehmann

Till the time I am in the container:  the container was running : as soon as i exited the terminal, the container terminated too.

### 8.) To troubleshoot use 
docker logs <contaner-id / name>

### 9.) docker inspect <container-id>
