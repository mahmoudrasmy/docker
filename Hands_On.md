
# Hands_on Docker

## First Lal (Create a Reddis Docker)
 - To search for a Docker image ===> $docker search redis
 - To Run a Container Redis (if the image doesn't exist it will download it) ===> $sudo docker run -d redis
 - To list all running Containers ===> $sudo docker ps
 - To Get more information about a running container ===> $sudo docker inspect
 - To Get Logs about Docker container ===> $sudo docker logs container_name
 - Run the Docker and expose the port (all the IP address are mapped to the port) ===> $sudo docker run -d --name redisHostPort -p 6379:6379 redis:latest
 - Run the Docker and expose the port (specifying an IP)  ===> $sudo docker run -d --name redisHostPort -p 127.0.0.1:6379:6379 redis:latest
 - To Run a container based on a random port ====> $docker run -d --name redisDynamic -p 6379 redis:latest
 - To Get the exposed port of a container ===> $docker port redisDynamic 6379
 - To mount a volume ===> $docker run -d --name redisMapped -v /opt/docker/data/redis:/data redis
 - To Run Container in the Foreground ===> $sudo docker run -it ubuntu bash 
