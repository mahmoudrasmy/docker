# How To install Docker behind Proxy

 - $sudo mkdir -p /etc/systemd/system/docker.service.d
 - $sudo vi /etc/systemd/system/docker.service.d/http-proxy.conf
 - Add the content on the created file 
	```
	[Service]
	Environment="HTTP_PROXY=http://proxy.example.com:80/"
	```
 - $sudo vi /etc/systemd/system/docker.service.d/https-proxy.conf
 - Add the content on the created file
	```
	[Service]
	Environment="HTTPS_PROXY=https://proxy.example.com:443/"
	```
 - $sudo systemctl daemon-reload
 - $sudo systemctl restart docker
 - $systemctl show --property=Environment docker
 - $systemctl show --property=Environment docker
