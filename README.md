# Docker
Repository to hold my Docker commands, examples and Dockerfiles for future needs.

### Basics
An image is a template used to create containers.
Containers are running instances of images that are isolated and have their own environments and set of processes.

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

