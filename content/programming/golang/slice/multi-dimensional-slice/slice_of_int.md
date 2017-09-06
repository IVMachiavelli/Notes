---
title: "Slice of integer"
draft: false
---

Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Slice of Interger" header="Slice of Integer" theme="default" %}}
```go
func main() {

	transactions := make([][]int, 0, 3)

	for i := 0; i < 3; i++ {
		transaction := make([]int, 0, 4)
		for j := 0; j < 4; j++ {
			transaction = append(transaction, j)
		}
		transactions = append(transactions, transaction)
	}
	fmt.Println(transactions)
}
```
{{% /panel %}}