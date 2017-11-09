---
title: "Commit"
draft: false
---

{{% panel="Commit" header="Commit" theme="default" %}}
```bash
# Commit container
#              <Commit Message>      <Commit Author> <Container ID><New Name> 
docker commit -m="This is a message" -a="Author Name" 196e0ce0c9fb crazy_image
```
{{% /panel %}}

{{% panel="Save" header="Save" theme="default" %}}
```bash
# docker save as .tar file
#              <name .tar file><commited image>  
docker save -o crazy_image.tar crazy_image
```
{{% /panel %}}

{{% panel="Exporting & Loading" header="Exporting & Loading on remote system" theme="default" %}}
```bash
# Export the saved .tar file to another system for use.
scp crazy_image.tar 

# Now on remote system load the .tar file using docker
docker load -i ~/Projects/crazy_image.tar

# You can now run the container on the remote machine
docker run -it crazy_image
```
{{% /panel %}}
