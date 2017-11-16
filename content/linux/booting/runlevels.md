---
title: "Run Levels"
draft: false
---
```bash
SYSVINT
0 - HALT (Shutdown)
1 - Single User
2 - Multi-User (No network or remote filesystems)
3 - Full Multi-User (Including networking and remote filesystems)
4 - Unused
5 - X11 (Full Multi-User with desktop enviroment)
6 - Reboot
```
```bash
SYSTEMD
0 - Poweroff.target (Shutdown)
1 - rescue.target (Single User/Rescue Shell)
2 - multi-user.target (Non-Graphical, Full Network, Multi-User)
3 - Multi-User.target (Non-Graphical, Full Network, Multi-User)
4 - Multi-User.target (Non-Graphical, Full Network, Multi-User)
5 - graphical.target (Graphical Desktop, Multi-User)
6 - reboot.target (Reboot)    
```
