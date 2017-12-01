---
title: "Workflow"
date: 2017-11-30T21:13:46-07:00
draft: true
---



{{% panel="Typical Workflow" header="Typical Workflow" theme="default" %}}
```bash
# Create a new directory for the repo.
mkdir new_repo && cd new_repo

# Initializes empty git repositories. ~/new_repo/.git/
git init
```

```bash
# Add a file to the staging area.
git add README.txt
```

```bash
# Check changes since last commit.
git status
```

```bash
# Commit changes.
git commit -m "Updating README.md"
```

```bash
# Check log file 
git log
```
{{% /panel %}}

