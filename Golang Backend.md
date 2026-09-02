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

## Interfaces

An interface is a contract that groups multiple structs that share identical method signatures.

```go
type car interface {
	getSpeed() int
}

type bmw struct {
	wheels int
	horsePower int
}

type honda struct {
	wheels int
	horsePower int
}

type invalid_car struct{}

func (b bmw) getSpeed() int {
	return b.horsePower * (wheels + 1)
}

func (h honda) getSpeed() int {
	return h.horsePower * (wheels + 4)
}

func (i invalid_struct) getSpeed() int {
	return 0
}
```

## Errors

Go doesn't use a [[try/catch]] statement like [[Python]] or [[Javascript]], so instead, errors are literally just an interface that ships with functions if something goes wrong.

```go
func (u user) formatUser() (string, error) {
	username, err = getUsername(u.id)

	if err != nil { // this is the error
		return "", err
	}
	return username+u.id, nil
}
```

## Arrays + Slices

For the most part, you (I) will be using slices for 99% of the time as they are basically dynamic lists.

```go
myArray := []int
```

You can use the `make` keyword: 

```go
// func make([]Type, length of array, capacity)
mySlice := make([]int, 5, 10)
```

### Spread / Variadic

**Variadic** functions are functions that can pass in an arbitrary number of arguments. It uses `...` to declare that it accepts one or many of `type`.

```go
// function that returns a new string with all the connected strings
func connect(connectedStr ...string) string { // ... == variadic
    var tString string = ""
    for i := 0; i < len(connectedStr); i++ {
        tString = tString + " " + connectedStr[i]
    }
    return tString
}
```

**Spread** operator allows you to pass a slice into a variadic function. The syntax is just `...` right after the slice variable.

```go
sl := []string{"Hello", "My", "Name", "Is", "Harrison"}
t := connect(sl...) // the ... here is after the variable, so it runs the connect() function, passing in the slice.
```

## Loops

Loops are similar in C.

```go

for INITIAL; CONDITION; AFTER {
	// do smth
}
```

e.g:

```go
cash := 0

for i := 0; i < 10; i++ {
	cash += 1
}

fmt.Println(cash)
```

### For Each Loop (for x in range)

For loops can also help with convenience looping over a slice.

```go
oses := []string{"iPhone", "Android", "Windows", "Mac", "Linux"} // a slice of Operating System names


// for every operating system in "oses" slice, print the operating system
for _, o := range oses {
	fmt.Println(o)
}
```

## Maps (Hashmaps)

They are pretty much [[Dictionaries]] in Python, or hashmaps in other proglangs.

To create one:

`usernamePassword := make(map[string]string)`

```go
// usernamePassword["justharsiz"] = "password123"
```

To insert an element:

`myMap[key] = element`

To get an element:

`element = myMap[key]`

To delete an element:

`delete(m, key)`

To check if a key exists:

`element, ok := myMap[key]`

### If Exists (Maps)

With maps, you can check if an object exists in a map in multiple ways, but each way uses different types of memory in code. For example:

```go
people := make(map[string]bool)

if people[person] {
	// person exists
}
```

That can be kind of slow though, so instead it would be better to use an empty struct or bool.


**Bool:**

```go
people := make(map[string]bool)

if _, ok := people[person]; ok {
	// person exists
}
```

The boolean takes a single byte into memory just to check existence though, so you can go even more efficient with this using _empty structs_ that use no bytes in memory.

```go
people := make(map[string]struct{}{})

if _, ok := people[person]; ok {
	// person exists
}
```