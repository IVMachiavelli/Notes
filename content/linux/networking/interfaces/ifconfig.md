---
title: "ifconfig"
draft: false
---


{{% panel="ifconfig" header="ifconfig" theme="default" %}}
```bash
# Device up
ifconfig wlan0 up

# Device down
ifconfig wlan0 down

# Promiscuous mode on
ifconfig wlan0 promisc

Promiscuous mode off
ifconfig wlan0 -promisc 

# List all network devices (configured or not)
ifconfig -a

# Configure a device thats not active
# Make sure the broadcast matches the device ip address
ifconfig eth1 173.168.0.100 netmask 255.255.240.0 broadcast 173.168.0.255
```
{{% /panel %}}
