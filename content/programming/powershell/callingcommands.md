---
title: "Calling Commands"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Calling Commands" header="Calling Commands" theme="default" %}}

- PowerShell commands can be called by name or alias.
- Specifying parameters to PowerShell commands start with a dash
- Call a command using named parameters (recommended)

```powershell
# Using named parameters helps the "plain English" readability of your code.

Start-Process -Name powershell -ArgumentList '-File $'
```
```powershell
# You don't have to use the full parameter name. You only need to specify enough of the parameter name such that it's unique. Also, parameter names are not case sensitive.

Start-Process -fil powershell -arg '-command exit'
```
Instead of calling a command using named parameters, you can rely on positional parameters. However, this requires foreknowledge of the parameter positions. You're much safer using named parameters, and your code will be easier for yourself and other members of your team to read and make changes to.

Use positional parameters to call a command. The "first" parameter on Start-Process is the -FilePath parameter, pointing to the binary we want to invoke.
```powershell
Start-Process powershell
```
```powershell
# Use multiple positional parameters (-FilePath and -ArgumentList)

Start-Process powershell -File $HOME/path/to/file.ps1
```

```powershell
# How do I know which order positional parameters go in?
# ANSWER: Use 'Get-Help -Parameters -Name Start-Process'

Get-Help -Name Start-Process -Parameter *
```
Some commands have "switch" parameters, which means they're either enabled or disabled. You don't actually pass a value into switch parameters.

```powershell
# Example: The Start-Process command has a -Wait switch parameter, that pauses execution until the launched process has completed.

Start-Process -FilePath powershell -ArgumentList '-Command Start-Sleep -Seconds 1' -Wait
```
```powershell
# BONUS: Find all parameters that are switch parameters

(Get-Command).Parameters.Values | Where-Object -FilterScript { $PSItem.ParameterType -eq [switch] }
```
```powershell
# If you have an ambiguous command name, you can disambiguate by specifying the containing module as a prefix.

Microsoft.PowerShell.Utility\Write-Information -MessageData 'Testing'
```

Using PowerShell Splatting is a much cleaner way of calling PowerShell commands. There are two main benefits:

1. You can audit parameters prior to invoking a command.
2. Your code becomes more vertical vs. horizontal, which causes line wrapping

- PowerShell Splatting is really easy to use, and is supported starting with PowerShell v3.0. Simply build a HashTable (Dictionary) of key-value pairs, and then use the @ character to reference the variable name that contains the HashTable during a command invocation. If you encounter a "switch" parameter, set it to [boolean] $true or $false to enable / disable it.

```powershell
# Let's use PowerShell Splatting to launch a new PowerShell process.

$NewProcess = @{
  FilePath = 'powershell'
  ArgumentList = '-Command Start-Sleep -Seconds 1'
  Wait = $true
}
Start-Process @NewProcess
```

```powershell
# PowerShell commands support the notion of multiple "Parameter Sets". We can use the reflection capabilities of PowerShell to find out which commands have multiple Parameter Sets.

$ModdedCommands = Get-Command | Add-Member -MemberType ScriptProperty -Name ParameterSetCount -Value { $this.ParameterSets.Count } -PassThru | 
  Sort-Object -Descending -Property ParameterSetCount
$ModdedCommands | Select-Object -First 10 -Property Name, ParameterSetCount
```

```powershell
# It looks like Split-Path has the most Parameter Sets at 8. Let's explore the different command syntaxes we can use.

Get-Command -Name Split-Path -Syntax
Get-Command -Name Split-Path -ShowCommandInfo
```
```powershell
# This Parameter Set allows us to grab the Parent path of a path.

Split-Path -Path $HOME -Parent
```

```powershell
# This Parameter Set allows us to grab the "Leaf" of a Path.

Split-Path -Path $HOME -Leaf
```

```powershell
# Calling native commands is fairly straightforward

mkdir -p $HOME/oscon2017test
```
{{% /panel %}}