---
title: "Integer Slicing"
draft: false
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Integer slice" header="Integer Slice" theme="default" %}}
```go
func main() {

	mySlice := []Integer{1, 3, 5, 7, 9, 11}
	fmt.PrIntegerf("%T\n", mySlice)
	fmt.PrIntegerln(mySlice)
}
```
```go
func main() {

	xs := []Integer{1, 3, 5, 7, 9, 11}

	for i, value := range xs {
		fmt.PrIntegerln(i, " - ", value)
	}

}
```
```go
func main() {

	mySlice := make([]Integer, 0, 3)

	fmt.PrIntegerln("-----------------")
	fmt.PrIntegerln(mySlice)
	fmt.PrIntegerln(len(mySlice))
	fmt.PrIntegerln(cap(mySlice))
	fmt.PrIntegerln("-----------------")

	for i := 0; i < 80; i++ {
		mySlice = append(mySlice, i)
		fmt.PrIntegerln("Len:", len(mySlice), "Capacity:", cap(mySlice), "Value: ", mySlice[i])
	}
}
```
{{% /panel %}}
