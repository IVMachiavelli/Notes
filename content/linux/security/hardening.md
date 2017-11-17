---
title: "Server Hardening"
draft: flase
---

{{% panel="SSH Security" header="SSH Security" theme="default" %}}
```bash
# Disable Root Login
vim /etc/ssh/sshd_config
# Now uncomment PermitRootLogin and change value to no
PermitRootLogin no
```

```bash
# Detailed SSH logging
vim /etc/ssh/sshd_config
# Change LogLevel to VERBOSE (all caps)
LogLevel VERBOSE
```
{{% /panel %}}


{{% panel="Kernal Security" header="Kernal Security" theme="default" %}}
```bash
vim /etc/sysctl1.conf
```
```
# Now ass the lines below
# Avoid a smurf attack
net.ipv4.icmp_echo_ignore_broadcasts = 1

# Turn on protection for bad icmp error messages
net.ipv4.icmp_ignore_bogus_error_responses = 1

# Turn on syncookies for SYN flood attack protection
net.ipv4.tcp_syncookies = 1

# Turn on and log spoofed, source routed, and redirect packets
net.ipv4.conf.all.log_martians = 1
net.ipv4.conf.default.log_martians = 1

# No source routed packets here
net.ipv4.conf.all.accept_source_route = 0
net.ipv4.conf.default.accept_source_route = 0

# Turn on reverse path filtering
net.ipv4.conf.all.rp_filter = 1
net.ipv4.conf.default.rp_filter = 1

# Make sure no one can alter the routing tables
net.ipv4.conf.all.accept_redirects = 0
net.ipv4.conf.default.accept_source_redirects = 0
net.ipv4.conf.all.secure_redirects = 0
net.ipv4.conf.default.secure.redirects = 0

# Don't act as a router
net.ipv4.ip_forward = 0
net.ipv4.conf.all.send_redirects = 0
net.ipv4.conf.default.send_redirects = 0

# Turn on execsheild for reducing worm or other automated remote attacks
kernel.exec-shield = 1
kernel.randomize_va_space = 1

# Tune IPv6
net.ipv6.conf.default.router.solicitations = 0
net.ipv6.conf.default.accept_ra_rtr_pref = 0
net.ipv6.conf.default.accept_ra_pinfo = 0
net.ipv6.conf.default.accept_ra_defrtr = 0
net.ipv6.conf.default.autoconf = 0
net.ipv6.conf.default.dad_transmits = 0
net.ipv6.conf.default.max_addresses = 1

# Increase system file descriptor limit
fs.file-max = 65535

# Allow for more PIDs (Prevention of fork() failure error message)
kernel.pid_max = 65536

# Increase system IP port limits
net.ipv4.ip_local_port_range = 2000 65000

# Tuning Linux network stack to increase TCP buffer size. Set the max OS send buffer size (wmem) and receive buffer size (rmem) to 12 MB for queues on all protocols.
net.core.rmem_max = 8388608
net.core.wmem_max = 8388608

# set minimum size, initial size and max size
net.ipv4.tcp_rmem = 10240 87380 12582912
net.ipv4.tcp_wmem = 10240 87380 12582912

# Value to set for queue on the INPUT side when incoming packets are faster then the kernel process on them.
net.core.netdev_max_backlog = 5000

# For increasing transfer window, enable window scaling
net.ipv4.tcp_window_scaling = 1
```
{{%/panel%}}

