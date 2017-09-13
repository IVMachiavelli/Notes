---
title: "Managing Modules"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Managing Modules" header="Managing Modules" theme="default" %}}

There are two types of PowerShell modules:

- Script
- Binary

```powershell
# You can search for and install modules from the public-facing PowerShell Gallery. You can also set up a private NuGet feed and publish modules there. https://powershellgallery.com

# The PowerShellGet module is built-in to PowerShell 5.0+ and enables interaction with the PowerShell Gallery. Let's start off by exploring the commands exposed by this module.

Get-Command -Module PowerShellGet
```
------------

```powershell
# Search for a module names Emojis

Find-Module -Name Emojis
```
------------
```powershell
# See if there are other versions of the module

Find-Module -Name Emojis -AllVersions
```
------------

```powershell
# Search for modules using wildcards

Find-Module -Name *emo*
```
------------
```powershell
# Search for modules using a common tag

Find-Module -Tag queue
```
------------
```powershell
# Search for modules using more than one tag

Find-Module -Tag queue, cloud
```
------------

```powershell
# Installing a module is easy, using the Install-Module command. You can install modules into your user directory (non-root) or install them for all users (requires root).

Install-Module -Name Emojis -Scope CurrentUser -Force
```

------------

```powershell
# See which modules were installed using PowerShellGet

Get-InstalledModule
```
------------

```powershell
# Remove a module that was installed using PowerShellGet. 

Uninstall-Module -Name Emojis -AllVersions -Force
```

{{% notice note%}}
This doesn't work for modules that were installed using a mechanism other than PowerShellGet.
{{% /notice %}}

------------

```powershell
# You can set up an internal NuGet feed and set it up as a private artifact repository

Register-PSRepository -Name MyCoolFeed -SourceLocation https://path.to/repo -PublishLocation https://path.to/nuget/feed
```
-----------
{{% /panel %}}
