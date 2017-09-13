---
title: "Strings"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Strings" header="Strings" theme="default" %}}


In PowerShell, there are a couple different ways of defining strings.

'Single-quoted strings can contain double quotes "like this"'

"Double-quoted strings can contain single quotes 'like this'"

"Double-quoted strings are handy, but should be avoided because variables like $ErrorActionPreference will get interpolated."

'If you use single-quoted strings, you get a literal representation of text, like $Host or $(Get-ChildItem).'

```powershell
# In double-quoted strings, you can add special characters

# Add a tab to your string

"`tTrevor"
```

```powershell
# Add a new-line to your string

"Trevor`nDaniel"
```

```powershell
# In PowerShell, you use the -f operator to invoke .NET String Formatting. By using template strings,
# you produce more predictable and reusable strings, compared to getting accidental interpolation 
# with double-quoted strings.

'{0}/../Tests/Unit.Tests.ps1' -f $PSScriptRoot
```

Here-Strings

```powershell
# A single-quoted here-string can contain single quotes without having to double them up.

$Command = @'
Set-Content -Path 'This is a really long path.txt' -Value
'@
Invoke-Expression -Command $Command
```

```powershell
# Keep in mind that double-quoted here-strings still perform variable and subexpression expansion

@"
$((Get-Process).Name)
"@
```

```powershell
# Regular expression matches

$Sentence = 'Trevor is excited to show others how to use PowerShell!'
$DidMatch = $Sentence -match 'Trevor'
```

```powershell
# The $matches automatic variable contains match results

if ($DidMatch) {
  $matches
}
```

```powershell
# Now we'll do a regular expression match against an array of strings (think grep)

$NameList = @'
Trevor
Daniel
Laken
James
Evelyn
Ariel
Adam
'@
```

```powershell
# A regular expression match against an array returned matching lines.

$NameList.Split("`n") -match 'e'
```
{{% /panel %}}
