---
title: "For With Continue"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="For With Continue" header="For With Continue " theme="default" %}}

```go
func main() {
	i := 0
	for {
		i++
		if i%2 == 0 {
			continue
		}
		fmt.Println(i)
		if i >= 50 {
			break
		}
	}
}
```
{{% /panel %}}
