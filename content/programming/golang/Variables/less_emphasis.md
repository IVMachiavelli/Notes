---
title: "Less Emphasis"
draft: false
weight: 3
---
Source: https://github.com/GoesToEleven/GolangTraining
{{% panel="Declare Variable" header="Declare Variable" theme="default" %}}
```go
func main() {
	var message string
	message = "Hello World."
	fmt.Println(message)
}
```
{{% /panel %}}

{{% panel="Declare Variable" header="Declare Multiple Variables" theme="default" %}}
```go
func main() {
	var message string
	var a, b, c int
	a = 1

	message = "Hello World!"

	fmt.Println(message, a, b, c)
}
```
```go
func main() {

	var message = "Hello World!"
	var a, b, c int = 1, 2, 3

	fmt.Println(message, a, b, c)
}
```
{{% /panel %}}


{{% panel="Infer Type" header="Infer Type" theme="default" %}}
```go
func main() {

	var message = "Hello World!"
	var a, b, c = 1, 2, 3

	fmt.Println(message, a, b, c)
}
```
{{% /panel %}}

{{% panel="Infer Type (Mixed Types)" header="Infer Type (Mixed Types)" theme="default" %}}
```go
func main() {

	var message = "Hello World!"
	var a, b, c = 1, false, 3

	fmt.Println(message, a, b, c)
}
```
{{% /panel %}}

{{% panel="init Shorthand" header="init Shorthand" theme="default" %}}
```go
func main() {

	// you can only do this inside a func
	message := "Hello World!"
	a, b, c := 1, false, 3
	d := 4
	e := true

	fmt.Println(message, a, b, c, d, e)
}
```
{{% /panel %}}

{{% panel="All together" header="All together" theme="default" %}}
```go
var a = "this is stored in the variable a"     // package scope
var b, c string = "stored in b", "stored in c" // package scope
var d string                                   // package scope

func main() {

	d = "stored in d" // declaration above; assignment here; package scope
	var e = 42        // function scope - subsequent variables have func scope:
	f := 43
	g := "stored in g"
	h, i := "stored in h", "stored in i"
	j, k, l, m := 44.7, true, false, 'm' // single quotes
	n := "n"                             // double quotes
	o := `o`                             // back ticks

	fmt.Println("a - ", a)
	fmt.Println("b - ", b)
	fmt.Println("c - ", c)
	fmt.Println("d - ", d)
	fmt.Println("e - ", e)
	fmt.Println("f - ", f)
	fmt.Println("g - ", g)
	fmt.Println("h - ", h)
	fmt.Println("i - ", i)
	fmt.Println("j - ", j)
	fmt.Println("k - ", k)
	fmt.Println("l - ", l)
	fmt.Println("m - ", m)
	fmt.Println("n - ", n)
	fmt.Println("o - ", o)
}
```
{{% /panel %}}
