---
title: "Multiple Evaluations"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Multiple Evaluations" header="Multiple Evaluations" theme="default" %}}
```go
func main() {
	switch "Jenny" {
	case "Tim", "Jenny":
		fmt.Println("Wassup Tim, or, err, Jenny")
	case "Marcus", "Medhi":
		fmt.Println("Both of your names start with M")
	case "Julian", "Sushant":
		fmt.Println("Wassup Julian / Sushant")
	}
}
```
{{% /panel %}}