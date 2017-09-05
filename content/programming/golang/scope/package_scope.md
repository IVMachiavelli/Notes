---
title: "Package_scope"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Package Scope" header="Package Scope" theme="default" %}}
```go
var x = 42

func main() {
	fmt.Println(x)
	foo()
}

func foo() {
	fmt.Println(x)
}
```
```go
package main

import (
	"fmt"
	"github.com/GoesToEleven/GolangTraining/04_scope/01_package-scope/02_visibility/vis"
)

func main() {
	fmt.Println(vis.MyName)
	vis.PrintVar()
}
```
```go
package vis

// MyName is exported because it starts with a capital letter
var MyName = "Todd"
var yourName = "Future Rock Star Programmer"
```
```go
package vis

import "fmt"

// PrintVar is exported because it starts with a capital letter
func PrintVar() {
	fmt.Println(MyName)
	fmt.Println(yourName)
}
```
{{% /panel %}}
