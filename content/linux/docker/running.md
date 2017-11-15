---
title: "Run"
draft: false
weight: 2
---

{{%notice info %}}
I will be using the debian container as an example to continue from the docker pull examples.
{{%/notice%}}

{{% panel="Docker Run" header="Docker Run in interactive mode" theme="default" %}}
```bash
# Run a container in interactive mode(tty)
docker run -it debian
OR
docker run debian /bin/bash

# Common options
-v Mount a volume to a container
-t Attach a pseudo-tty to a container
-i Make container interactive (stdin open)
-m Constrain memory for a container
-c Increase containers CPU priority
--name='name' Set custom name of the container
-e Set env variable container process sees
--entrypoint Override containers entrypoint
-h Set hostname within the container
-p Map container port to a host port
-P true Publish all contaier ports to host
-rm Remove container when it exits
```
{{% /panel %}}

{{% panel="Docker Run" header="Mapping ports" theme="default" %}}
```bash
# The first port is the host, the second is the container
docker run -p 80:80 debian
# http://localhost:80
```
```bash
# Another example mapping a host port to a container port
docker run -p 9119:80 debian
# http://localhost:9119/
```

{{% /panel %}}

{{% panel="Docker Run" header="Docker Run in detached mode" theme="default" %}}
Running the container in the background known as ```--detach``` mode.
```bash
docker run -d debian
or
docker run --detach debian
```
{{% /panel %}}

{{% panel="Docker Run" header="Attach to container" theme="default" %}}
```bash
# Attach to a running container
docker attach debian
```
{{% /panel %}}
