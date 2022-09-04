# docker-cheatsheet
##Docker Cheatsheet

`docker run <hello-world>` - attempt to run a docker container called `hello-world` image. It first look `image` locally, if not exist, it pulls `image` from dockerhub. <br/>
`docker ps` - list running docker containers
<br/>
`docker ps --all | -a` - list all docker containers
<br/>
`docker create <hello-world>` -  Create a new container
<br/>
`docker start <container id>` - Start one or more stopped containers, add `... start -a ...` to attached to a container
<br/>
`docker stop <container id>` - stop docker container (send sigterm message or terminate signal). This allows container to gracefully exit in 10 seconds
<br/>
`docker kill <container id>` - force stop docker container
<br/>
`docker system prune` - removing all stopped docker containers
<br/>
`docker logs <container id>` - retrieving logs output
<br/>
`docker exec -it <container id> | <image name> <command>` | `winpty docker exec ...` (in windows gitbash) - Run a command in a running container e.g `docker exec -it 0ebdadaefb9a redis-cli` which exec `redis-cli` in running redis container. `-it` is short command for `-i` (Keep STDIN open even if not attached / attached command to redis container) and `-t` to make text beautifier (text autocomplete/indentation etc).
<br/>
<br/>
`docker exec -it <container id> | <image name> sh ` | `winpty docker exec ...` (in windows gitbash) - Full terminal access inside the container. E.g  `winpty docker exec -it 0ebdadaefb9a sh` wherein `0ebdadaefb9a` is the container id of redis container. By running this, i already get full access into redis cli in the running container. `sh` is a shell or command processor.
<br/>
<br/>
`docker run -it busybox sh` - alternative to `docker exec` but preferred `docker exec`
<br/>
`docker build .` - generate docker image / build project into a docker image

