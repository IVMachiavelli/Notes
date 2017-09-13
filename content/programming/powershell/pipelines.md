---
title: "Pipelines"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Pipelines" header="Piplines" theme="default" %}}

The PowerShell pipeline is useful for writing one-liners interactively, though I recommend avoiding the use of the.

```powershell
# The ForEach-Object is frequently used to iterate over objects. You can specify a "begin" ScriptBlock, that runs once, before any objects in the pipeline are processed. Next, you specify the -Process ScriptBlock, which runs once for each item. To reference the "current" item, use the $_ or $PSItem automatic variables. Finally, the -End ScriptBlock runs commands after all the objects have been processed.
Get-Process | ForEach-Object -Begin { $Names = @() } -Process { $Names += $PSItem.Name } `
  -End { $Names } | Sort-Object
```

```powershell
# The percent sign is the default alias for ForEach-Object. The first positional parameter to this command is the -Process ScriptBlock.

Get-Process | % { $PSItem.Name + ' ' + $PSItem.Id }
```

```powershell
# This is the short-hand equivalent of the first command above, using positional parameters instead.

gps | % { $Names = @() } { $Names += $PSItem.Name } { $Names }
```

```powershell
# The Where-Object command is used to filter objects in a pipeline. Remember, in PowerShell we're dealing with objects, not parsing text.

# Although it is easier to read the fully expanded version of this command, there are short-hand ways of calling this. While there are more complex versions of this command, the basic invocation is straightforward, using the -FilterScript parameter. This parameter is a ScriptBlock that should return either $true or $false.

Get-Process | Where-Object -FilterScript { $PSItem.Name -match '^s' }
```

```powershell
# The question mark is the default command alias for Where-Object. The first positional parameter is the -FilterScript ScriptBlock. The $_ and $PSItem automatic variables are interchangeable, where they're applicable.

Get-Process | ? { $_.Name -like '*a*' }
```

```powershell
# You can specify multiple conditions inside the -FilterScript ScriptBlock.

Get-ChildItem -Recurse | Where-Object -FilterScript { $PSItem.PSIsContainer -and $PSItem.Name -match 'powershell' }
```
{{% /panel %}}
