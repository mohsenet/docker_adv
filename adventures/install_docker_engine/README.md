
# Installing Docker Engine

Installing Docker Engine on Ubuntu 22.04 (Jammy Jellyfish) involves a few straightforward steps.

```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
sudo systemctl start docker
sudo systemctl enable docker
sudo docker run hello-world
```

# Installing Docker with Snap

```bash
sudo apt update
```

ensure snapd is installed
```bash
sudo apt install -y snapd
```

Ensure snapd is running:
```bash
sudo systemctl enable --now snapd
```

Install Docker via Snap
```bash
sudo snap install docker
```

Check Docker version:
```bash
docker --version
```

Run a test container:
```bash
sudo docker run hello-world
```

