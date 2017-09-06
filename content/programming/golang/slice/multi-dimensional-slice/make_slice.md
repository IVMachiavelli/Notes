---
title: "Make Slice"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Make Slice" header="Make Slice" theme="default" %}}
```go
func main() {
	student := make([]string, 35)
	students := make([][]string, 35)
	fmt.Println(student)
	fmt.Println(students)
	fmt.Println(student == nil)
}
```
{{% /panel %}}
