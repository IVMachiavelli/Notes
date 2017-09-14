---
title: "Error Handling"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Exception Handling" header="Exception Handling" theme="default" %}}

```powershell
# Error handling in PowerShell can be a little tricky, so pay special attention to this section of the workshop!

$VerbosePreference = 'continue'
```

```powershell
# In the original version of PowerShell, you would use a "trap" statement to catch errors that occurred in your scripts.

thiscommanddoesntexist

trap {
  Write-Host -Object 'Something bad happened! Let''s handle it here.'
}
```


Newer versions of PowerShell support try..catch statements IMPORTANT: There's a difference between "terminating" and "non-terminating errors." The try..catch statement will ONLY catch "terminating" errors.

```powershell
# Example: Non-terminating Errors
try {
  Get-Command -Name thisdoesntexist
}
catch {
  Write-Verbose -Message 'This catch handler won''t be invoked.'
}
```

```powershell
# We need to turn the non-terminating error into a terminating error. To do this, either: 1) add "-ErrorAction Stop" to the command invocation, or set $ErrorActionPreference = 'Stop'

try {
  Get-Command -Name thisdoesntexist -ErrorAction Stop
}
catch {
  Write-Verbose -Message 'This catch handler will be invoked.'
}
```

```powershell
# The built-in (automatic) $Error variable is appended to when an exception occurs

$Error[0] | Get-Member
$Error[1]
```

```powershell
# How many errors have occurred in this PowerShell session?

$Error.Count
```

You can also ignore error messages in a couple of different ways.

```powershell
# Example: I don't care if this command doesn't exist .. keep executing. In this example, the error won't be written to the Error stream, but it will appear in the $Error variable.

Get-Command -Name thisdoesntexist -ErrorAction SilentlyContinue
```

```powershell
# In this example, the error won't be written to the Error stream, and it will NOT appear in the $Error variable.

Get-Command -Name thisdoesntexist -ErrorAction Ignore
```
Both the 'SilentlyContinue' and 'Ignore' values are supported in $ErrorActionPreference
{{% /panel %}}