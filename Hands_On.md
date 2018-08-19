
# Hands_on Docker

## First Lab (Create a Reddis Docker)
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


## General commands
 - $sudo docker --version
 - $sudo docker info
 - $sudo docker run hello-world
 - $sudo docker image ls   ==> to list all images 
 - $sudo docker container ls --all   ==> to list all containers
 
 ## Fastest Way to deploy your app in a docker container 
  - Create a Dockerfile and put the below content into it 
    ```
    # Use an official Python runtime as a parent image
    FROM python:2.7-slim
    # Set the working directory to /app
    WORKDIR /app
    
    # Copy the current directory contents into the container at /app
    ADD . /app
    
    # Install any needed packages specified in requirements.txt
    RUN pip install --trusted-host pypi.python.org -r requirements.txt
    
    # Make port 80 available to the world outside this container
    EXPOSE 80
    
    # Define environment variable
    ENV NAME World
    
    # Run app.py when the container launches
    CMD ["python", "app.py"]
    ```
  - $sudo docker build -t friendlyhello .  ==> to build an image
  - $sudo docker run -p 4000:80 friendlyhello   ==> to run a container instance 
  - $sudo docker run -d -p 4000:80 friendlyhello  ==> to run a container instance in deatched mode
