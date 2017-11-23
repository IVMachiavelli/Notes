---
title: "Dockerfile"
draft: false
---

- Order of execution: When writing a Dockerfile the order of execution goes from top down and is important to remember when writing more advanced docker deployments.

- CMD VS RUN:
  - CMD: This command runs everytime the container is instantiated.
  - RUN: Only runs during the build process.

- FROM Sets the Base Image for subsequent instructions.
- MAINTAINER (deprecated - use LABEL instead) Set the Author field of the generated images.
- RUN execute any commands in a new layer on top of the current image and commit the results.
- CMD provide defaults for an executing container.
- EXPOSE informs Docker that the container listens on the specified network ports at runtime. NOTE: does not actually make ports accessible.
- ENV sets environment variable.
- ADD copies new files, directories or remote file to container. Invalidates caches. Avoid ADD and use COPY instead.
- COPY copies new files or directories to container. Note that this only copies as root, so you have to chown manually regardless of your USER / WORKDIR setting. See https://github.com/moby/moby/issues/30110
- ENTRYPOINT configures a container that will run as an executable.
- VOLUME creates a mount point for externally mounted volumes or other containers.
- USER sets the user name for following RUN / CMD / ENTRYPOINT commands.
- WORKDIR sets the working directory.
- ARG defines a build-time variable.
- ONBUILD adds a trigger instruction when the image is used as the base for another build.
- STOPSIGNAL sets the system call signal that will be sent to the container to exit.
- LABEL apply key/value metadata to your images, containers, or daemons.

{{% panel="FROM" header="FROM" theme="default" %}}
```bash
FROM debian:latest
```
{{% /panel %}}

{{% panel="LABEL" header="LABEL" theme="default" %}}
```bash
# LABEL with contact info and description.
LABEL maintainer="github.com/ivmachiavelli"
description="Just an example Dockerfile"
```
{{% /panel %}}

{{% panel="RUN" header="RUN" theme="default" %}}
```bash
# Run update with -y flag to accept all.
RUN apt-get update && apt-get upgrade -y
```
{{% /panel %}}

{{% panel="EXPOSE" header="EXPOSE" theme="default" %}}
``` bash
```
{{% /panel %}}

{{% panel="CMD" header="CMD" theme="default" %}}
```bash
# Echo out a welcome command once container is instantiated
CMD "echo" "Welcome, This is a ruby develepment container"
```
{{% /panel %}}

{{% panel="ENTRYPOINT" header="ENTRYPOINT" theme="default" %}}
```bash
# Using the ruby irb as an ENTRYPOINT
ENTRYPOINT irb
```
{{% /panel %}}

{{% panel="COPY" header="COPY" theme="default" %}}
```bash
# Copying from the host machine to the image
COPY files/nginx.conf /etc/nginx/nginx.conf
```
{{% /panel %}}

{{% panel="ENV" header="ENV" theme="default" %}}
```bash
# Syntax: <key> <value>
ENV JAVA_BIN /usr/java/jdk.1.8.0/jre/bin
```
{{% /panel %}}



{{% panel="ENV" header="ENV" theme="default" %}}
```bash
# Syntax: <key> <value>
ENV JAVA_BIN /usr/java/jdk.1.8.0/jre/bin
```
{{% /panel %}}

{{% panel="Adding Non Privilaged User" header="Adding Non Privililaged User" theme="default" %}}
```bash
# Adding a user ivmachiavelli
RUN useradd -ms /bin/bash ivmachiavelli

# Defining which user to use.
# This should be the last command in the order of execution. So that all other commands can be executed as root.
USER ivmachiavelli
```
{{% /panel %}}
