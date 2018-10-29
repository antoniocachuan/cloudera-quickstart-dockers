# Big Data as a Service, get easily running a Cloudera Quickstart Image with Dockers in GCP
## article published in Data Science Central 
####Install docker
```
curl -sSL https://get.docker.com/ | sh
```
####Update the package database with the Docker package
```
sudo apt-get update
```
####Get the Cloudera Quickstart Image
```
sudo wget https://downloads.cloudera.com/demo_vm/docker/cloudera-quickstart-vm-5.13.0-0-beta-docker.tar.gz
```
####Extract the tar file
```
tar xzf cloudera-quickstart-vm-*-docker.tar.gz
```
####Import the docker *maybe you could run out of space in that case remove the tar.gz file an re run the import
```
sudo docker import cloudera-quickstart-vm-5.13.0-0-beta-docker.tar
```
####Check the container image ID
```
sudo docker images
```
####Run the container 
```
sudo docker run --hostname=quickstart.cloudera --privileged=true -t -i -p 8777:8888 -p 7190:7180 -p 90:80 b46c7719892d /usr/bin/docker-quickstart
```
####Test services
```
spark-shell
hive
hbase shell
```
####Run in background
```
sudo docker run --hostname=quickstart.cloudera --privileged=true -t -i -p 8777:8888 -p 7190:7180 -p 90:80 b46c7719892d /usr/bin/docker-quickstart -d
sudo docker ps 256e31278a92
sudo docker attach 256e31278a92
```

###Links
(https://www.theserverside.com/feature/The-benefits-of-container-development-with-Docker)
(http://community.cloudera.com/t5/CDH-Manual-Installation/CDH-on-Kubernetes/td-p/64772)
(https://github.com/apache-spark-on-k8s/spark)
(https://conferences.oreilly.com/strata/strata-ny-2018/public/schedule/detail/69534)
(https://cloud.google.com)
(https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)
(https://www.cloudera.com/documentation/enterprise/5-6-x/topics/quickstart_docker_container.html)
