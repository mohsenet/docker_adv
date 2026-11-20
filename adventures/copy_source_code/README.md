### You can copy the source code from your container
```bash
docker exec -it CONTAINER_NAME bash
```

```bash
cd ~/frr
docker cp CONTAINER_NAME:/app ./recovered_source
ls -la ./recovered_source
```

You should see:
```text
app.py
lesson.py
message.py
config.py
requirements.txt
```
