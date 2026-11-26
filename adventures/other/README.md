

remote registry

local registry


### Docker Images

Images stored in these path
```bash
cd /var/lib/docker/
```

List all downloaded images
```bash
sudo docker images
```

Where the actual layers live on disk
```bash
sudo ls -la /var/lib/docker/overlay2/
```

Better Way to Access Your Containers/Images
```bash
# All downloaded images
sudo docker images

# All running containers
sudo docker ps

# All volumes (your MySQL/ES/MinIO data lives here)
sudo docker volume ls

# Inspect a specific container (shows mounts, IP, image, etc.)
sudo docker inspect docker-ragflow-cpu-1

# See the actual on-disk path of a volume
sudo docker volume inspect docker_mysql_data
```

Switch to `official Docker CE`
```bash
# Remove snap version
sudo snap remove docker

# Install official Docker Engine
sudo apt update
sudo apt install -y ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
  sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu jammy stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

