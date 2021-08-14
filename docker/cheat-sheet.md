# Run, build or stop image

`docker-compose -f <docker.yml> --project-name <project_name> <build|up|down>`

# Erase
How to erase images, containers and volumes.

## Images
`docker rmi -f $(docker images -a -q)`

## Containers
`docker rm $(docker ps -a -q)`

## Volumes
`docker volume rm $(docker volume ls -q)` or `docker rm -f -v {{postgres_container_name}}`

# Prune
`docker system prune [OPTIONS]`. [Link](https://docs.docker.com/engine/reference/commandline/system_prune/)

# Kill all Docker containers
`docker kill $(docker ps -q)`

# Allow ssh to local machine (Ubuntu)
`sudo ufw allow ssh`
