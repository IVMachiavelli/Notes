---
title: "Commit"
draft: false
---

Source:https://docs.docker.com/engine/reference/commandline/commit/#description
{{% panel="Docker Commit" header="Docker Commit" theme="default" %}}
In this example we will run a Debian container, make some changes, then commit those changes.
```bash
# Run a debian container.
docker run -it debian /bin/bash
```
```bash
# Update and install git
apt update && apt install git
```

```bash
# exit the container, container will continue to run in the background
exit
```

```bash
# Check running containers.
docker ps -a
```

```bash
# Check what changes have been made.
docker diff d67bc5094d42
```

```bash
# Commit the changes to a new container ready to be pushed.
# docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
docker commit d67bc5094d42 ivmachiavelli/debian_git:1.0
```
{{% /panel %}}
