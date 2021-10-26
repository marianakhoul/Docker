# Docker
Repository to hold my Docker commands, examples and Dockerfiles for future needs.

### Basics
An image is a template used to create containers.
Containers are running instances of images that are isolated and have their own environments and set of processes.

### Volume Mounting

The container has a layered architecture.
In the writable layer, data is stored and there are temporary files.
The container layer only lives while the container is alive.
All modifications to files happens in the container layer, and all data will be removed from the container.
To preserve the data, need to add a persistent layer.
Default files created under: /var/lib/docker -- stores volumes, images and files

Step 1. Create volume using docker volume create under /var/lib/docker/volumes/data_volume
Step 2. docker run -v data_volumes:/var/lib/mysql mysql

Can run step 2 alone and docker will automatically mount the data.
Need to specify the full path if data_volume is outside of /var/lib/docker/volumes -- this is called bind mounting

Can add other variables to the bind mounting
```
docker run --mount type=bind, source=/data/mysql, target=/var/lib/mysql --name $Name_of_container
```

### Basic Commands

Run image
```
docker run $image_name
```
List all running containers
```
docker ps
```
Lists even the stopped containers
```
docker ps -a
```
Stop an image
```
docker stop $container_id or docker stop $image_name
```
Delete/remove container
```
docker rm $image_name
```
Delete image
```
docker rmi $image_name
```
List of available images
```
docker image
```
Download image but doesn't run it
```
docker pull $image_name
```
Execute a command on a running container
```
docker exec $image_name Enter-bash-command
```
Detatch an image (runs in the backend) to be able to still use the terminal or logout
```
docker run -d $image_name
```
Attach a detatched container
```
docker attach $image_name
```
Run versions of images usng tagging
```
docker run redis:4.0
```
Run using stdin -t is pseudo terminal and -i is interactive
```
docker run -it $image_name
```
Port mapping
```
docker run -p 80:5000 $image_name
```
Volume Mapping
```
docker run -v /opt/datadir:/var/lib/mqsql mysql
```
More details about the container
```
docker inspect $image_name
```
Container logs of a detached container
```
container logs $image_name
```

