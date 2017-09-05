---
title: "Less Emphasis"
draft: false
weight: 3
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Declare Variable" header="Declare Variable" theme="default" %}}
```go
func main() {
	var message string
	message = "Hello World."
	fmt.Println(message)
}
```
{{% /panel %}}

{{% panel="Declare Variable" header="Declare Multiple Variables" theme="default" %}}
```go
func main() {
	var message string
	var a, b, c int
	a = 1

	message = "Hello World!"

	fmt.Println(message, a, b, c)
}
```
```go
func main() {

	var message = "Hello World!"
	var a, b, c int = 1, 2, 3

	fmt.Println(message, a, b, c)
}
```
{{% /panel %}}
