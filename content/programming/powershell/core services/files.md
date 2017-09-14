---
title: "Files"
draft: false
---


Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Working with Files" header="Working with Files" theme="default" %}}

PowerShell provides a series of standard commands that allow you to read from and write to files.

```powershell
# Get the file contents of yourself (the script you're running).

$Me = Get-Content -Path $MyInvocation.MyCommand.Path
$Me.Count
```

```powershell
# Get the file contents as a single string, using the -Raw parameter

$Me = Get-Content -Path $MyInvocation.MyCommand.Path -Raw
$Me.Count
```

```powershell
# Write some text to a file

Set-Content -Path $HOME/setcontent.txt -Value 'Welcome to OSCON!'
```

```powershell
# Write some text to a file
# IMPORTANT: Note the default encoding of Out-File vs. Set-Content

'Welcome to OSCON!' | Out-File -FilePath $HOME/outfiletest.txt
```

```powershell
# List the immediate children of a path

Get-ChildItem -Path $HOME
```

```powershell
# Recursively get the child files / folders

Get-ChildItem -Path $pwd -Recurse
```

```powershell
# Get only the child directories of a path (excludes files)

Get-ChildItem -Path $HOME -Directory
```

```powershell
# Delete a file

Remove-Item -Path 
```

```powershell
# Create a folder (uses the native Linux / Mac OS X command, not a PowerShell command)

$FolderPath = "$HOME/oscon-deleteme"
mkdir $FolderPath
```

```powershell
# See if the folder exists (should be True)

Test-Path -Path $FolderPath -PathType Container
```

```powershell
# Delete the folder

Remove-Item -Path $FolderPath -Recurse -Force
```

```powershell
# Create a new item (file or folder) 

New-Item -Path $HOME/oscon-newitem.txt -ItemType File
```

```powershell
# Create a new directory the "PowerShell way"

New-Item -Path $HOME/oscon-newdirectory -ItemType Directory
```
{{% /panel %}}
