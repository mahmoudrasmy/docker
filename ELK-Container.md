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
	
5-To login to the container : 
	$sudo docker exec -it elk /bin/bash
	
	 /opt/logstash/bin/logstash --path.data /tmp/logstash/data -e 'input { stdin { } } output { elasticsearch { hosts => ["localhost"] } }'
	 
6-To query the Elastic-Search use this URL : http://IP:9200/_search?pretty
	 
	 
