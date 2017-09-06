---
title: "While"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="For Conditional" header="For Conditional (While-ish) " theme="default" %}}

Go only has the ***for loop***, however we can use it like a while loop if needed.
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
