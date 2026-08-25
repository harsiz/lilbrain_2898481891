Go (GoLang) is a programming language made to be really fast and useful for certain web backend applications.

## Printf
Go has a similar Printf to [[C Programming]] and how C handles prints (e.g: `%d`, `%v`)

To print in golang, you use `fmt` (formatting) package.

```go
package main

import fmt

func main() {
	fmt.Printf("Hello there I am %v years old!", 34)
}
```

## Conditionals

Golang has similar conditionals to [[C Programming]] but don't require brackets in them. Golang also doesn't require semi-colon.

`if length > 3 { doSomething }`

### Initial Statement

The initial statements of `if` blocks can keep variables to the scope of the _if statements_ AND just looks cleaner.

```go
if age:=yourAge(user); age < 18 {
	fmt.Printf("Your age: %d, is too young to view.", age)
}
```

compared to using it without initial statement:

```go
age := yourAge(user)
if age < 18 {
	fmt.Printf("Your age: %d, is too young to view.", age)
}
```