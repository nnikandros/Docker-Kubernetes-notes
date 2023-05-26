
# Introduction
The following means we want to start up a new container using the image with the name hello-world
`docker run hello-world`

## Lifecycle of a container

`docker run = docker create + docker start`

To stop a process we 

- `docker stop <container id>`or 
- `docker kill <container id> `

Stop will allow 10 seconds for the daemon to stop the process safely. Kill will stop execution immediatly. We prefer `stop`.

# Basic manipulation of containers

`docker version`

`docker run busybox echo how are you?`

`docker run busybox ls` - list directories that exists solely on that container

`docker ps` list all different containers present on our machine

After a container stops we can find all past containers by 

`docker ps -all`

Then with the `id` of the container we can rerun it by `docker start <id>` or `docker start -a <id>`

`docker create hello-world` this will give a container id

And then we can do `docker start -a <container id>` (-a watch for output and print on terminal )

The command `docker system prune`: will remove 
- all stopped containers
- all networks not used by at least one container
- all images
- all build cache

