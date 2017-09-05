---
title: "Init condition post"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Basic For Loop" header="Basic For Loop" theme="default" %}}
```go
func main() {
	for i := 0; i <= 100; i++ {
		fmt.Println(i)
	}
}
```
{{% /panel %}}

{{% panel="Nested For Loop" header="Nested For Loop" theme="default" %}}
```go
func main() {
	for i := 0; i < 5; i++ {
		for j := 0; j < 5; j++ {
			fmt.Println(i, " - ", j)
		}
	}
}
```
{{% /panel %}}

{{% panel="For Loop (use as While loop)" header="While Loop" theme="default" %}}

Go doesn't actually have a ***while loop*** (only for loop), However we can use it in a similar way.
```go
func main() {
	i := 0
	for i < 10 {
		fmt.Println(i)
		i++
	}
}
```
{{% /panel %}}


{{% panel="No Condition" header="No Condition" theme="default" %}}
```go
func main() {
	i := 0
	for {
		fmt.Println(i)
		i++
	}
}
```
{{% /panel%}}
