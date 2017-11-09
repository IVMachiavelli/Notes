---
title: "Utilities"
draft: false
---
{{% panel="CPU Architecture" header="CPU Architecture" theme="default" %}}
```bash
# CPU Architecture Information
lscpu

# 
lscpu -ae

# display in (parse format)
lscpu --parse
```
{{% /panel %}}


{{% panel="Kernel Modules Status" header="Kernel Modules Status" theme="default" %}}
```bash
lsmod
```
{{% /panel %}}

{{% panel="PCI Bus" header="PCI Bus" theme="default" %}}
```bash
# PCI Buses (-v verbose -mm machine readable)
lspci -vmm
```
{{% /panel %}}

{{% panel="Block Devices" header="Block Devices" theme="default" %}}
```bash
# List block Devices (-l list format)
lsblk -l

# List Block Devices (-f file system)
lsblk -f

# List Block Devices (-t tree format)
lsblk -t
```
{{% /panel %}}

{{% panel="SCSI" header="SCSI" theme="default" %}}
```bash
# SCSI Devices (-s size) 
lsscsi -s

# SCSI Devices (-g generic) 
lsscsi -g 


# SCSI Devices (-vv verbose) 
lsscsi -vv
```
{{% /panel %}}


{{% panel="USB Devices" header="USB Devices" theme="default" %}}
```bash
# USB Devices (-t tree)
lsusb -t


# USB Devices (-v verbose)
lsusb -v

# USB Devices (-s show only with select ID)
# Example: displays only Dev 5
lsusb -s 5
```
{{% /panel %}}

