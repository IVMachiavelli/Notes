---
title: "Encrypt Folders"
draft: false
---

Reference: https://wiki.archlinux.org/index.php/ECryptfs#Encrypting_a_data_directory
{{% panel="ecryptfs" header="ecryptfs" theme="default" %}}
```bash
modprobe ecryptfs
# Check to see if it's running
lsmod | grep ecryptfs
```
```bash
# Add non-root users if required
vim /etc/group
```

```bash
# Setting up Private folders
# The --noautomount flag turns off automatically mount on user login.
ecryptfs-setup-private --noautomount

# cat out generated passphrase
cat ~/.ecryptfs/wrapped-passphrase

# Check for Private & .Private(Encrypted) folders
ls -al
```

Understanding the Private folders
Place files in the Private folder then unmount.

```bash
# Mount the folders
mount.ecryptfs_private
```
{{% /panel %}}
