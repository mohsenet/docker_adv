### Configure a Registry Mirror (ir)

Create or modify the `/etc/docker/daemon.json` file:
```bash
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://registry.docker.ir"]
}
EOF
```

Reload the configuration and restart Docker
```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
```

Verify the configuration is in effect
```bash
docker info | grep -A2 "Registry Mirrors"
```

test
```bash
docker run hello-world
```

