---
title: "If not"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="if not" header="if not" theme="default" %}}
```go
func main() {

	if !true {
		fmt.Println("This did not run")
	}

	if !false {
		fmt.Println("This ran")
	}

}
```
{{% /panel %}}