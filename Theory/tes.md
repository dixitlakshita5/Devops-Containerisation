notes -containers are made on terminal
-docker is run with root privilege / shared kernel
-sudo is written to give access/ rootaccess
-different containers will have diff hash like “987dd8cf9508”

how to install WSL on mac 

after installing WSL 

run  commands

wsl //to switch to wsl
sudo apt update && sudo apt install docker.io -y


docker -v //to see if docker is installed or not 

₹sudo docker ps₹ //list of containers run by the docker 

docker images  // to see docker images on our system, docker downloaded it with docker pull, even if the system is offline we can use these images that are present in out system 

docker pull ubuntu // name of ubuntu image - ubuntu, it will it pull it from docker hub the latest image 

docker pull ubuntu:22.04 //want to use this version as base image 

//if we want to know what version are available we can go to docker hub, it will be by the name “supported tags and respective Dockerfile links”

docker rmi ubuntu //rmi means remove image if we dont need the image anymore or is consuming too much, image will not be removed if it is already in use 

-f// force image removal 
-a // remove unused images 

docker run ubuntu //
common flags 
-it // switch to current container 
 —name mycontainer nameofcontainer //to give name to the container
—d // detached (background) , current container will not run it will be in background
—rm //auto-remove container after exit 

docker run -it —name ?

docker ps // list running containers
docker ps -a // stopped containers list 

//if we want to remove we can remove containers by their hash 
//if we dont assign name to docker it will by default assign any random name like strange_swi etc

Start/Stop/Restart 