## Install Official Docker for Ubuntu 26.04

### remove any older or unofficial Docker-related packages to avoid conflicts:
```bash
sudo apt remove $(dpkg --get-selections docker.io docker-compose docker-compose-v2 docker-doc docker-buildx podman-docker containerd runc | cut -f1)
```

### Install the necessary prerequisites and add Docker's official GPG key:
```bash
sudo apt update
sudo apt install -y ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### add the repository to your APT sources. The command below automatically detects your Ubuntu codename (which should be `resolute` for 26.04):
```bash
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF
```

### After adding the repository, update the package index again:

```bash
sudo apt update
```

### Install the Docker packages (including the CLI, containerd, Buildx, and Compose plugins):
```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
```bash
sudo systemctl status docker
```

### you need sudo to run Docker commands. To run them as a regular user, add your user to the docker group:
```bash
sudo usermod -aG docker $USER
```

### Run the classic test container to confirm everything is working:
```bash
docker run hello-world
```

