---
title: "Switch"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Switch Statement" header="Switch Statement" theme="default" %}}
```go
func main() {
	switch "Mhi" {
	case "Daniel":
		fmt.Println("Wassup Daniel")
	case "Medhi":
		fmt.Println("Wassup Medhi")
	case "Jenny":
		fmt.Println("Wassup Jenny")
	default:
		fmt.Println("Have you no friends?")
	}
}
/*
  no default fallthrough
  fallthrough is optional
  -- you can specify fallthrough by explicitly stating it
  -- break isn't needed like in other languages
*/
```
{{% /panel %}}