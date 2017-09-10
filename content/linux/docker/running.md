---
title: "Run"
draft: false
weight: 2
---

{{%notice info %}}
I will be using the debain container as an example to continue from the docker pull examples.
{{%/notice%}}

Source:https://docs.docker.com/engine/reference/commandline/run/#options
{{% panel="Docker Run" header="Docker Run in interactive mode" theme="default" %}}
Running a container in interactive mode(TTY) 
```bash
docker run -it debain
```
OR
```bash
docker run debain /bin/bash
```
{{% /panel %}}

{{% panel="Docker Run" header="Docker Run in detached mode" theme="default" %}} 
Running the container in the background known as --detach mode. 
```bash
docker run -d debain
```
{{% /panel %}}

{{% panel="Docker Run" header="Docker Run in interactive mode" theme="default" %}} 
Running the container in the background known as --detach mode. 
```bash
docker run -d debain
```
{{% /panel %}}


