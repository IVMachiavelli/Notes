---
title: "Fallthrough"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Fallthrough" header="Fallthrough" theme="default" %}}
```go
func main() {
	switch "Marcus" {
	case "Tim":
		fmt.Println("Wassup Tim")
	case "Jenny":
		fmt.Println("Wassup Jenny")
	case "Marcus":
		fmt.Println("Wassup Marcus")
		fallthrough
	case "Medhi":
		fmt.Println("Wassup Medhi")
		fallthrough
	case "Julian":
		fmt.Println("Wassup Julian")
	case "Sushant":
		fmt.Println("Wassup Sushant")
	}
}
```
{{% /panel %}}