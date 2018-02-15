# Hello Docker Ubuntu

A simple Tutorial on how to start a container and to save its state to be re-usable on ubuntu

## List of commands used in this tutorial

* To Search for a specific image from Docker Hub : $docker search ubuntu
* To Download the image for the Docker Hub : $docker pull ubuntu
* To list all available images in your local Repository : $docker images
* To run the image in an interactive mode : $docker run -it ubuntu
* Make a change in your container, for example you can setup nodejs by using the following commands
	* $apt-get update 
	* $apt-get install -y nodejs
	* Copt the ID of your container session, for example : root@87948b32a4af:, 87948b32a4af is your container ID
	* $exit
* Save the changes that you have made to your container by using this command: $docker commit -m "added node.js" -a "you name" 87948b32a4af ubuntu-nodejs