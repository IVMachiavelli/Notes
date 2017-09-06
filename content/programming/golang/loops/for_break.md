---
title: "For With Break"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="For With Break" header="For with break statement" theme="default" %}}
```go
func main() {
	i := 0
	for {
		fmt.Println(i)
		if i >= 10 {
			break
		}
		i++
	}
}
```
{{% /panel %}}