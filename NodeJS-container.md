# Containrize Nodejs image
================================
# Prerequiste
============
1-Get Ubuntu image 
2-Install Docker on the ubuntu image 
3-install nodejs on ubuntu
-------------------------------------------

# Steps

1-Install nodejs on Ubuntu
	1.1-$sudo apt-get update
	1.2-$sudo apt-get install nodejs
	1.3-$sudo apt-get install npm

2-First create the nodejs application
	1.1-create the package.json
		{
			"name": "docker_web_app",
			"version": "1.0.0",
			"description": "Node.js on Docker",
			"author": "SMS",
			"main": "server.js",
			"scripts": {
			"start": "node server.js"
			},
			"dependencies": {
			"express": "^4.16.1"
			}
		}
	
 	1.2-Create the script server
	  'use strict';
      const express = require('express');
      // Constants
      const PORT = 8080;
      const HOST = '0.0.0.0';

      // App
      const app = express();
      app.get('/', (req, res) => {
      res.send('Hello world\n');
      });
 
      app.listen(PORT, HOST);
      console.log(`Running on http://${HOST}:${PORT}`);
	  
	  1.3-Run the script file using the following command
		$nodejs server.js
		
3-Create the Docker File
	1-$touch Dockerfile
	2-Copy the following script in the docker file 
		FROM node:carbon
		# Create app directory
		WORKDIR /usr/src/app
		
		# Install app dependencies
		# A wildcard is used to ensure both package.json AND package-lock.json are copied
		# where available (npm@5+)
		COPY package*.json ./
		
		RUN npm install
		# If you are building your code for production
		# RUN npm install --only=production
		
		# Bundle app source
		COPY . .
		
		EXPOSE 8080
		CMD [ "npm", "start" ]
	3-$touch .dockerignore
	4-Copy the following script inside the .dockerignore
		node_modules
		npm-debug.log
	5-Build the image using the following command
		$docker build -t <your username>/node-web-app .
	6-Run the image using this command
		$docker run -p 49160:8080 -d <your username>/node-web-app
	7-To go inside the container
		$docker exec -it <container id> /bin/bash

## Refrences
https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
