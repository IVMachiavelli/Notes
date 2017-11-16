---
title: "Tor"
draft: false
---

{{% panel="Tor Basics" header="Tor Basic" theme="default" %}}
Tor config files can be found at /etc/tor/torrc
```bash
# Starting the tor service
sudo sytemctl start tor
# Tor default port 9050

# Check tor status
sudo systemctl status tor
```
{{% /panel %}}


{{% panel="Tor Server" header="Tor Server" theme="default" %}}
```bash
# Configure /etc/tor/torrc to listen on a specific network address 
# To listen on all interfaces
SocksListenAddress 0.0.0.0

# Or on a specific address
SocksListenAddress 192.164.0.1

# Change the port
SocksListenAddress 192.164.0.1:9934

# Tor needs to be restarted for settings to take effect
sudo systemctl restart
```
{{% /panel %}}
