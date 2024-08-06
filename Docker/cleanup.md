### single command that will clean up any resources — images, containers, volumes, and networks

`docker system prune -a`

### cleanup containers

`docker container rm -f $(docker container ls -aq)`

### cleanup images

`docker image rm -f $(docker image ls -f reference='*' -q)`
`docker rmi $(docker images -a -q)`