---
title: "Int Slice++"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Int Slice++" header="Int Slice++" theme="default" %}}
```go
func main() {
	mySlice := make([]int, 1)
	fmt.Println(mySlice[0])
	mySlice[0] = 7
	fmt.Println(mySlice[0])
	mySlice[0]++
	fmt.Println(mySlice[0])
}
```
{{% /panel %}}
