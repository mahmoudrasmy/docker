# Elastic Search -Logstash - Kibana container :
==============

## Prerequiste
------------
1-an Ubuntu image <br />
2-install Docker Engine

## Usage
-------
1-$sudo sysctl -w vm.max_map_count=262144 <br />
2-$sudo docker pull sebp/elk <br />
3-$sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it --name elk sebp/elk <br />
4-Notes :
	-Port 5601 is for Kibana
	-Port 9200 is for Elasticsearch
	-Port 5044 is for Logstash
	
	34.230.39.250:5601
	90c581d74e79
	sudo docker exec -it elk /bin/bash
	
	 /opt/logstash/bin/logstash --path.data /tmp/logstash/data -e 'input { stdin { } } output { elasticsearch { hosts => ["localhost"] } }'
	 
	 http://107.22.17.59:9200/_search?pretty
	 
	 10.176.246.114:3000
	 
	 34.230.39.250:5601
	 
	 
