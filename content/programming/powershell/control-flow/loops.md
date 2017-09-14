---
title: "Loops"
draft: False
---

# A simple for loop
for ($i = 0; $i -le 20; $i++) {
  $i
}

# A simple foreach loop
foreach ($Process in (Get-Process)) {
  $Process.Name
}

# A simple while loop
while ((Get-Date).Second % 10 -ne 0) {
  Write-Host -Object 'The current second is not a multiple of 10.'
  Start-Sleep -Seconds 1
}

# Do loops are guaranteed to execute at least once
do {
  Write-Host -Object 'The current second is not a multiple of 10.'
  Start-Sleep -Seconds 1
} while ((Get-Date).Second % 10 -ne 0)

# PowerShell has a built-in "Where" and "ForEach" method that can be chained together
# somewhat similarly to a PowerShell pipeline.
# These methods are available on any IEnumerable (array, list, dictionary / HashTable, etc.).
(Get-Process).Where({ $PSItem.Name -match '^m' }).ForEach({ $PSItem.Name })
```
{{% /panel %}}