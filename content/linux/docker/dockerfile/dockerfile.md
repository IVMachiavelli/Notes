---
title: "Dockerfile"
draft: false
---

{{% panel="Example Dockerfiles" header="Example Dockerfiles" theme="default" %}}
```bash
FROM httpd:2.4

LABEL maintainer="ivmachiavelli"

RUN apt-get update && apt-get install fortunes

COPY script.sh ~/home

EXPOSE 80
```
{{% /panel %}}



