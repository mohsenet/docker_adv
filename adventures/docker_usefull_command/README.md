## List Docker Images

List all images
```bash
docker images
```

Or using the newer syntax
```bash
docker image ls
```

List all images (including intermediate layers)
```bash
docker images -a
```

List images with specific format
```bash
docker images --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"
```



## List Docker Containers

List running containers
```bash
docker ps
```

Or using the newer syntax
```bash
docker container ls
```

List all containers (running and stopped)
```bash
docker ps -a
```

List containers with specific format
```bash
docker ps --format "table {{.Names}}\t{{.Status}}\t{{.Ports}}"
```



## Additional Useful Options

Show image sizes in human-readable format
```bash
docker images --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"
```

Filter images by name
```bash
docker images nginx
```

Show dangling images (untagged)
```bash
docker images -f "dangling=true"
```



## For Containers

Show only container IDs
```bash
docker ps -q
```

Show latest created container
```bash
docker ps -l
```

Filter containers by status
```bash
docker ps -f "status=running"
docker ps -f "status=exited"
```

Filter containers by name
```bash
docker ps -f "name=container_name"
```

Count running containers
```bash
docker ps -q | wc -l
```

Count all images
```bash
docker images -q | wc -l
```
