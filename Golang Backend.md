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

### Switch/Case

Similar to [[Python]]'s match case (and C's switch case)

```go
var day int

switch day {
	case 1:
		fmt.Printf("First day")
	case 2:
		fmt.Printf("Second day")
	case 3:
		fallthrough // fallthrough just drops down to the next case
	case 4:
		fallthrough
	case 5:
		fmt.Printf("3 thru 5th day.")
	case 6:
		fallthrough
	case 7:
		fmt.Printf("6 thru 7th")
	default:
		fmt.Printf("Unrecognized day")
}
```

## Functions

Functions in Go start with the `func` keyword.

```go
func greeting(name string) string { // the final "string" is the return value type
	var goStr string = fmt.Sprintf("Hello there %s, how are you?")
	return goStr
}
```

With Go functions, you **MUST** include the full function signature (including the return type and the argument types.)

## Structs

Golang structs are similar to classes, they help group stuff together.

```go
type user struct {
	name string
	id int
}
```

You can also use dot notation when assigning to a variable

```go
user1 := user{
	name: "john_doe",
	id: 256, // defining doesnt require commas, assigning does
}
```