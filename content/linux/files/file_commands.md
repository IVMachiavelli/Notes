---
title: "File Commands"
draft: false
---

{{% panel="Listing Files" header="Listing Files" theme="default" %}}
```bash
# List files 
ls

# Display hidden files (.dotfiles)
ls -a

# List files and permissions 
ll

# List hidden files and permissions
ls -al
```
{{% /panel %}}


{{% panel="Navigation" header="Navigation" theme="default" %}}
```bash
# Change Directory
cd /etc/

# Go back one directory
cd ..

# Go back to home
cd
```
{{% /panel %}}}


{{% panel="" header="Navigation" theme="default" %}}
```bash
# Copy files (cp <filename> <to_directory>)
cp /ruby/working_project ~/project_backup

# mv (mv <filename> <to_directory>)
mv /ruby/working_project ~/completed_projects

# Rename a file (mv <filename> <changed_filename>)
mv hosts hosts.txt

# Delete Files (rm <filename>)
rm hosts.txt

# Delete entire directory
rm -rf *

# Delete entire directory with prompt with -i flag
rm -rfi *
```
{{%/panel %}}

