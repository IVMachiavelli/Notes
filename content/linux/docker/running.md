---
title: "Run"
draft: false
weight: 2
---

{{%notice info %}}
I will be using the debian container as an example to continue from the docker pull examples.
{{%/notice%}}

Source:https://docs.docker.com/engine/reference/commandline/run/#options
{{% panel="Docker Run" header="Docker Run in interactive mode" theme="default" %}}
Running a container in interactive mode(TTY) 
```bash
docker run -it debian
```
OR
```bash
docker run debian /bin/bash
```
{{% /panel %}}

{{% panel="Docker Run" header="Docker Run in detached mode" theme="default" %}} 
Running the container in the background known as ```--detach``` mode. 
```bash
docker run -d debian
```
{{% /panel %}}

Source: https://docs.docker.com/engine/reference/commandline/attach/#override-the-detach-sequence1
{{% panel="Docker Run" header="Attach to container" theme="default" %}} 
Attach to a running container, running in detached mode. 
```bash
docker attach debian
```
{{% /panel %}}


