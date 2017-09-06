---
title: "Nested"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
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

