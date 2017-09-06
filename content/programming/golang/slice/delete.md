---
title: "Delete"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Delete" header="Delete" theme="default" %}}
```go
func main() {

	mySlice := []string{"Monday", "Tuesday"}
	myOtherSlice := []string{"Wednesday", "Thursday", "Friday"}

	mySlice = append(mySlice, myOtherSlice...)
	fmt.Println(mySlice)

	mySlice = append(mySlice[:2], mySlice[3:]...)
	fmt.Println(mySlice)

}
```
{{% /panel %}}
