---
title: "Working with Modules"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Working with Modules" header="Working with Modules" theme="default" %}}

PowerShell modules are the mechanism to author and package a set of common functionality and share it within your team, organization, or with the world.

------------

```powershell
# List the modules installed on the system in $env:PSModulePath Short-hand: gmo -list

Get-Module -ListAvailable
```

------------

```powershell
# List the modules currently imported into the session

Get-Module
```

------------

```powershell
# Import the Emojis PowerShell module.

Import-Module -Name Emojis
```
{{% notice note %}}
NOTE: Normally, PowerShell module auto-loading will load the module for you, but if you've disabled module auto-loading, then you'll need to explicitly import modules.
{{% /notice %}}

------------

```powershell
# Inspect the commands that are in the Emojis module.

Get-Command -Module Emojis
```

------------

```powershell
# A module is an object, just like any other object in PowerShell.

$MyModule = Get-Module -Name Emojis -ListAvailable
$MyModule | Select-Object -Property *
```

------------

```powershell
# You can create dynamic, in-memory PowerShell modules using the New-Module command. The help documentation for New-Module is helpful in learning how this works.

Get-Help -Name New-Module -Detailed
```

------------

```powershell
# Let's create a new module with a single function.

New-Module -Name OSCON -ScriptBlock {
  function Add ($x,$y) { $x + $y }
} | Import-Module
```
{{% /panel %}}
