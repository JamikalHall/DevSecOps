learning GO:

young programming language, created in 2009.

Why GO?

> personal reasons: cool cloud tech is written in Go, like Terraform and Kubernetes

main use case for Go: 
- writing performant applications that run on scaled, distributed systems (cloud)
the goal of Go was to create a language that has the readable syntax of something like Python, with the safety and efficiency of something like C++.

Go is good for creating microservices, web apps and DB services.

Go code is a compiled language, i.e. it is transformed into machine code before running. this means you get consistency across different OSes. 

---

Common practice to name the main file of the application `main.go`

Go provides several packages out of the box to use. 

		> A pacakge is a collection of source files
		> 'fmt' package provides several functionalities related to formatting (print, reading I/O, etc)

Go programs must have at least one with:
- 'main' package
- main function > this is the where the program starts.
```go
package main

import 'fmt'

func main(){
	fmt.print ("Hello World!)
}
```

All Go files start with package. This defines the namespace for the code. The `main` package is special since it indicates that the file belongs to an executable program.   

To execute a Go file from the cmd: `go run main.go`

---
Go Syntax:

to declare a variable:

var | name | type

variables that are not initialized with a value have a value of 0.

**int** = integers. these can go up to 64. The bigger the integer you specify, the bigger a number that can be stored. ints will default to either 32 or 64 depending on the architecture of your system.
- you can also store uint, or unsigned integers. these only allow positive values, so you can store twice the size of a number in the same space.

**float** = number with decimal.

**string** = combination of letters.

**bools** = true or false.

shorthand for declaring variables:

name | := | value

You can also declare multiple variables at once using the same shorthand:

var1, var2 := 1, 2

would initialize two variables at the same time.

**const** = constant variable whose value does not change. this variable must be initialized at time of creation.

creating a function:

```go
func main(){
	printMe()
}

func printMe(){
	fmt.Println("Hello World")
}
```

the syntax above will create a function called printMe that will just print 'hello world'

I can give it a parameter as well by passing it in the parentheses.

```go
func main(){
	printMe()
}

func printMe(printValue string){
	fmt.Println(printValue)
}
```

When defining functions that returns something, you have to specify the return value at the end of the function.

```go
func main(){
	printMe()
}

func intDivision(numerator int, denominator int) int {
	var result int = numerator/denominator
	return result
}
```

Takeaway:

This is just day one of experimenting with Go. I have written code before, so I am familiar with coding concepts such as these. I will be continuing to learn Go and applying it where I can to build apps, APIs, and automations. I plan to also work with Python as well.
