# Docker File 
	* A text document file to automate the build of a customized image 
	
## Most used commands during image building

	* First create a file and call it Dockerfile
	* To build an image use the following command :
		$docker build -t name_of_the_future_image .
	
	* To run an image
		$docker run --name name_of_the_container -i -t -d image_name
	
	* To access the container using SSH
		$docker exec -u 0 -it my_ubnuntu bash
	


