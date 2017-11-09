---
title: "Common Command Line"
draft: false
---


{{% panel="Common Use" header="Common Use" theme="default" %}}
```bash
# get help using: <command> -h
man -h # Example

# use man pages using: man <command>
man man # Example

# search man with -k flag
man -k users | grep 8

# update man
sudo mandb

# Display logged in user
whoami

# Check history
history

# Run previous history command
!436

# pipe to less to display content page by page
nmap -h | less

# Display current system date
date

# Display operating system information
uname -a # -a flag for all

# Change password
passwd

# Check login history
last

# Check login history by ip
last -i
```
{{% /panel %}}


{{% panel="hostname" header="hostname" theme="default" %}}
```bash
# Display hostname
hostname

# Display hostname IP's
hostname -i

# Display DNS domain name
hostname -d
```
{{% /panel %}}
