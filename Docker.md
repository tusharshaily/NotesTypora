# Docker

## Docker commands

- docker images -> to get all the images 
- docker ps -> to get all the running containers
- docker ps -a ->  to get all the containers present on the system that are either running or not running
- docker run -d image_name -> to run the container
- docker start container_id to start  to particular container
- docker stop container_id to stop the particular container
-  

![image-20220629192526489](/home/tushar/.config/Typora/typora-user-images/image-20220629192526489.png)



- docker run -pLaptopPort:ContainerPort -d imagenames

## Docker Image 

- docker logs ID/names
- To give the you custom name to the container use = **docker run -d IMAGE --name CUSTOMNAME**
-  To access the container terminal : **docker exec -it ID{NAME} /bin/bash**

![image-20220629200949248](/home/tushar/.config/Typora/typora-user-images/image-20220629200949248.png)



![image-20220629201037389](/home/tushar/.config/Typora/typora-user-images/image-20220629201037389.png)



so docker makes isolated networks too, we get the docker network : **docker network ls** 

to create the network use : **docker network create NAME OF THE NETWORK**

So when both the containers are in the same network then , so can directly use the name of the containers

for connection 

when we run the containers , if we get into the documentation then see there are **Enviroment variabls ** that we need to set
