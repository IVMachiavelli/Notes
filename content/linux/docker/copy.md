---
title: "Copy Files"
draft: false
---

{{% panel="Copy from host machine" header="Copy from host machine" theme="default" %}}
Copy a file from the host machine to a running docker container.
```bash
docker cp <file> container_name:</full/dir/path/in/container>
```
```bash
# Example
docker cp ~/script.sh ubuntu:/home/  
```
{{% /panel %}}

