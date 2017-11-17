---
title: "Build"
draft: false
---

{{% panel="Example Dockerfiles" header="Example Dockerfiles" theme="default" %}}
```bash
# Basic dockerfile build
docker build -t .
```

```bash
# Building a tagged(named) docker image
docker image build --tag web-server:1.0 .
```
{{% /panel %}}
