# POC HDFS, Spark and Jupyter integration with Docker

This POC based on [docker-hadoop-spark-workbench](https://github.com/thuongdinh/docker-hadoop-spark-workbench)

## Target
 - Run HDFS, Spark and Jupyter Notebook with docker/docker-compose
 - Note: Spark cluster will run standalone mode (not support YARN or Mesos)

## Requirements
 - Docker version 1.12.3
 - Docker Compose version 1.8.1

## Basic docker up

1. Up docker-compose

	```
	$ docker network create hadoop
	$ docker-compose up -d
	```

2. Browse Web UI for components:
 - Jupyter Notebook: http://localhost:8889
 - Hue (HDFS Manager): http://localhost:8088/home
 - Hadoop Dashboard: http://localhost:50070
 - Spark Master: http://localhost:9090/

## Scale Spark

```
$ docker-compose up -d
$ docker-compose scale spark-worker=2
```

Open Spark Master: http://localhost:8080/ to see 2 workers added to the master.