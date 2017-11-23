---
title: "Git"
draft: false
---

{{% panel="Git Setup" header="Git Setup" theme="default" %}}
```bash
# Git User name.
git config --global user.name "John Doe"
```
```bash
git config --global user.email "John_Doe@gmail.com"
```
```bash
# git Colors
git config --global color.ui true
```

{{% /panel %}}

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
