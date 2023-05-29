
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


The following command will retrieve all logs from a container. We do not start or create a new containter. just printing what it has already printed 
`docker logs <container id> `


## Multi command containters
Execute an additional command inside a container.

`docker exec -it <container id> <command>`
This fllowing mean:
1. exec means run another command
1. -it allows us to provide input to the container

For example we want to run rediss-cli in a a container running redis-server. In order to have acess to the redis-cli we need to run

`docker exec -it e49f3926e387 redis-cli`

In reality `-it` are two commands:
1. `-i` is giving command to take stdin
2. `-t` to make things formatted and nice (essentialy)

To run shell in a container we can do the following: 

```docker exec -it e49f3926e387 sh```

We can create a containter that only has a shell inside it by doing the following

``` docker run -it busybox sh ```

But most commonely we will use the `docker exec...` comamand since that command allows us to run a process in a container and have a shell.

## Container Isolation


# Building custom images

## creating docker images

## Building a docker file

## whats a base image 

## build process in detail 