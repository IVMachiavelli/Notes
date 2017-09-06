---
title: "Init Statement"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Initialization statement" header="Initialization Statement" theme="default" %}}
```go
func main() {

	b := true

	if food := "Chocolate"; b {
		fmt.Println(food)
	}

}
```
{{% /panel %}}
{{% panel="Initialization statement (Error Invalid Code)" header="Initialization statement (Error Invalid Code)" theme="default" %}}
```go
func main() {

	b := true

	if food := "Chocolate"; b {
		fmt.Println(food)
	}

	fmt.Println(food)

}
```
{{% /panel %}}

