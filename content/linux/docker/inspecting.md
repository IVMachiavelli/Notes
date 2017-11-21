---
title: "Inspecting"
draft: false
---

{{% panel="Inspecting" header="Inspecting a docker container" theme="default" %}}
```bash
# Inspect all information
docker inspect debian

# Inspect process ID of container
docker inspect --format 

# Inspect IP Address
docker inspect --format='{{.NetworkSettings.IPAddress}}' debian

# Inspect bridge
docker inspect --format='{{.NetworkSettings.Bridge}}' debian

# Inspect Ports
docker inspect --format='{{.NetworkSettings.Ports}}' debian

# Inspect Binds
docker inspect --format='{{.NetworkSettings.Binds}}' debian

# Inspect PID
docker inspect --format='{{.State.Pid}}' debian

# Attach to container
nsenter -m -u -n -i -p -t 1841
```
{{% /panel %}}

```bash
docker image inspect -f {{.Config.Labels}} <IMAGE ID>
```
