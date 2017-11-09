---
title: "Stop"
draft: false
---

Source:https://docs.docker.com/engine/reference/commandline/run/#options
{{% panel="Stop Running Container" header="Stop Running Container" theme="default" %}}
```bash
# List running containers
docker ps

# List all containers
docker ps -a

# List running containers (Only container ID)
docker ps -a -q

# Stop running container
docker stop debain

# Start a stopped container
docker start zen_kare

# kill container
docker kill zen_kare

# Remove container
docker rm zen_kare
```
{{% /panel %}}
