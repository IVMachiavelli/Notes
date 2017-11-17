---
title: "Start & Stop"
draft: false
---

Source:https://docs.docker.com/engine/reference/commandline/run/#options
{{% panel="Start Stopped Container" header="Start Stopped Container" theme="default" %}}
```bash
# Start a stopped container
docker start zen_kare
```
{{% /panel %}}


{{% panel="Stop Running Container" header="Stop Running Container" theme="default" %}}
```bash
# Stop running container
docker stop debain
```
{{% /panel %}}


{{% panel="Attaching to a container as root" header="Attaching to a container as root" theme="default" %}}
```bash
# Connect to a running container as root user.
# User flag -u and 0 (0 is always root)
docker exec -u 0 -it zen_kare /bin/bash
```
{{% /panel %}}
