---
title: "Get-Command"
draft: false
weight: 2
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Get-Command" header="Get-Command" theme="default" %}}

PowerShell commands are, by convention, named using the Verb-Noun syntax.

```powershell
# Get a list of all commands available on the system.

Get-Command
```
------------

```powershell
# Retrieve a command by its name.
# NOTE: If there are ambiguous command names, more than one object may be returned.
#       For example, two different modules could expose a duplicate command name.

Get-Command -Name Select-Object
```

------------

```powershell
# Retrieve all commands that start with "select."

Get-Command -Name Select*
```

------------

```powershell
# Retrieve all commands from a particular module

Get-Command -Module Microsoft.PowerShell.Host
```
------------

- There are different types of commands available:
    - Cmdlets - Compiled .NET assemblies containing PowerShell commands
    - Advanced Functions - Script functions that use [CmdletBinding()] attribute
    - Aliases - PowerShell command aliases
    - Application - Native applications (ifconfig, bash, powershell, etc.)
    - Configuration - DSC configuration documents


```powershell
# Get alias commands

Get-Command -CommandType Alias
```
------------

```powershell
# Get native (non-PowerShell) commands matching a particular name

Get-Command -CommandType Application -Name *config*
```
------------

```powershell
# You can get commands from a specific module version, using a ModuleSpecification object
# For more information, see: Get-Help -Name Get-Command -Parameter FullyQualifiedModule

Get-Command -FullyQualifiedModule @{ ModuleName = 'Microsoft.PowerShell.Management'; ModuleVersion = '3.1.0.0' }
```
{{% /panel %}}