---
title: "Output"
draft: false
---
Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Output" header="Output" theme="default" %}}

PowerShell formatting helps you change the way objects are emitted to the PowerShell host.

```powershell
# Find formatting PowerShell cmdlets

Get-Command -Name Format*
```

------------

```powershell
# We can change the output to list format, which is better for "wide" object properties (eg. a log entry).

Get-Process | Format-List
```

------------

```powershell
# We can get all the properties from the objects, using the -Property parameter

Get-Process | Format-List -Property *
```

------------

```powershell
# We can also get specific properties by specifying an array of strings

Get-Process | Format-List -Property Cpu, Path, HasExited, *time*
```

------------

```powershell
# The default output of Get-Process is in a tabular format

Get-ChildItem | Select-Object -Property *
```

------------

```powershell
# Format content as a hexidecimal representation

Get-Content -Path $HOME/setcontent.txt | Format-Hex
```

------------

```powershell
# Let's grab some filesystem objects

Get-ChildItem -Path / | Select-Object -Property *
```

------------

```powershell
# But what if we want to make this more readable? Let's turn it into tabular output.

Get-ChildItem -Path / | Select-Object -Property * | Format-Table -AutoSize
```
{{% /panel %}}
