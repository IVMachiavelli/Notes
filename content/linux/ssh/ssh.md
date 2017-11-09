---
title: "SSH"
draft: false
---


{{% panel="SSH Keygen" header="SSH Keygen" theme="default" %}}
```bash
# Check for existing keys
ls ~/.ssh

# Generating new ssh keys
ssh-keygen -t rsa -b 4096 -C "email@address.com"
# You will then be prompted to store the key in a directory (default: ~/.ssh/id_rsa)

# Add SSH keys to SSH agent
ssh-add ~/.ssh/id_rsa

# Change SSH password
ssh-keygen -p
```
{{% /panel %}}


{{% panel="SSH Connecting" header="SSH Connecting" theme="default" %}}
```bash
# Connect to a server using specified port number
ssh -p 9824 user@164.169.164.255
```
{{% /panel %}}


{{% panel="SSH Security" header="SSH Security" theme="default" %}}
```bash
# edit the sshd_config file in /etc/ssh directory
vim sshd_config

# Change #PermitRootLogin to no (restart SSH service)
PermitRootLogin no

# Disable protocol 1 should be disabled by default, if not change to protocol 2
protocol 2

# Change to non-standard SSH port (Default SSH 22)
# Helps prevent SSH brute force / SSH scans
Port 8316
```
{{% /panel %}}
