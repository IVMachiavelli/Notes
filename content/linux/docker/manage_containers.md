---
title: "Manage Containers"
draft: false
---

{{% panel="Listing Containers" header="Listing Containers" theme="default" %}}
```bash
# List running containers
docker ps

# List all containers
docker ps -a

# List running containers (Only container ID)
docker ps -a -q
```
{{% /panel %}}

{{% panel="Kill / Remove Container" header="Kill / Remove Containers" theme="default" %}}
```bash
# kill container
docker kill zen_kare
```
```bash
# Remove container
docker rm zen_kare
```
{{% /panel %}}
