# How to Stop All Docker Containers

```bash
docker kill $(docker ps -q)
```

- `docker ps`: Lists all running containers. `-q` only return the container IDs.
- `docker kill`: Stops the continers by container ID.

## Remove all containers

```bash
docker rm $(docker ps -a -q)
```

- `docker ps -a -q`: Lists all containers (including non-running) and only return their IDs.
- `docker rm`: Remove containers by their ID.

## Remove all images

```bash
docker rmi $(docker images -q)
```

- `docker images -q`: Lists all images by their IDs.
- `docker rmi`: Removes docker images by their ID.
