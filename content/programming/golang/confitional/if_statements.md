---
title: "If Statements"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="if else" header="if else" theme="default" %}}
```go
func main() {

	if false {
		fmt.Println("first print statement")
	} else {
		fmt.Println("second print statement")
	}
}
```
{{% /panel %}}
{{% panel="else if" header="else if" theme="default" %}}
```go
func main() {

	if false {
		fmt.Println("first print statement")
	} else if true {
		fmt.Println("second print statement")
	} else {
		fmt.Println("third print statement")
	}
}
```
```go
func main() {

	if false {
		fmt.Println("first print statement")
	} else if false {
		fmt.Println("second print statement")
	} else if true {
		fmt.Println("ahahaha print statement")
	} else {
		fmt.Println("third print statement")
	}
}
```
{{% /panel %}}
