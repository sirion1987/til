# Connect to container

```
docker exec -ti <CONTAINER_ID> /bin/bash
```

# Show logs

```
docker logs <CONTAINER_ID> --follow
```

# Auto-restart

```
docker update --restart=no $(docker ps -a -q)
```
