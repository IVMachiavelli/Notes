---
title: "Get-Help"
draft: false
weight: 1
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Get-Help" header="Get-Help" theme="default" %}}
```powershell
# PowerShell Help pages are similar to man pages, but offer a richer experience.
# It's up to each PowerShell function / module developer to provide help.

Get-Help -Name Get-Help
```
------------

```powershell
# Get help for a PowerShell provider

Get-Help -Category Provider -Name Alias
```

------------

```powershell
# By default, you're shown consolidated help for PowerShell commands

Get-Help -Name Start-Process
```
------------

```powershell
# If you want a specific section of help, you can specify it:
#   - Parameters
#   - Detailed
#   - Full
#   - Examples

Get-Help -Name Start-Process -Detailed
```

------------

```powershell
# "Full" help includes examples, parameter help, etc.

Get-Help -Name Start-Process -Full
```

------------

```powershell
# Get help for all parameters on the command

Get-Help -Name Start-Process -Parameter *
```
------------

```powershell
# Get help for a specific parameter on the command

Get-Help -Name Start-Process -Parameter FilePath
```
{{% /panel %}}