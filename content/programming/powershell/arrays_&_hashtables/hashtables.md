---
title: "Hashtables"
draft: false
---

Source: https://github.com/pcgeek86/oscon-2017
{{% panel="Hashtables" header="Hashtables" theme="default" %}}
```powershell
# Arrays can contain any object type

$MyArray = @(1, 'OSCON', (Get-Process -Name powershell))
```

```powershell
# Inspect the array containing multiple object types

$MyArray | Get-Member
```
```powershell
# HashTables are key-value pairs (think Dictionary) with a string key and any object can be the value. You can also nest HashTables inside HashTables, arrays inside HashTables, and vice versa.

$MyHT = @{
    Manufacturer = 'Dell'
    Model = 'PowerEdge 6950'
    GuestVMs = @(
        @{
            OS = 'Ubuntu 16'
            Name = 'myubuntuvm'
        }
        @{
            OS = 'Ubuntu 17'
            Name = 'myzestyvm'
        }
    )
}
```
{{% /panel %}}
