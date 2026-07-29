C is a programming language known for being "high level" (it's not.)

```c
int main() {
	return 0;
}
```

That is the simplest C program. It is just returning "0" as the exit code. the `int` at the front is just like type hints, saying that an exit code will be returned.

## Print "Hello World"

```c
#include <stdio.h> \\ YOU MUST INCLUDE STANDARD INPUT OUTPUT (dot) HEADER

int main() {
	printf("Hello, world!\n");
	return 0;
}
```

## Basic Types & Extra Variable Jazz

`int` -> integer
`float` -> float / decimal
`char` -> singular character
`char *` ("string".. kind of, but mainly used as a string.)

Much like javascript, you can use: `const` as a prefix to defining variables to make them constant and error out if changed during runtime. E.g: ```
```c
const int lifetime = 73;
```

### Format Specifiers

When doing stuff (such as printing) you have to specify to C how to display the values being printed.

__Common Ones Include__:

`%d` -> digit (integer)
`%c` -> character (singular `char`)
`%f` -> floating point number (float)
`%s` -> string (okay so _here_ C recognises that strings exist but not in variables 😂)

E.g:

```c
#include <stdio.h>

int main() {
	char *videogame = "osu!";
	int *hours_playing = 46;
	printf("You've been playing %s for %d hours!!\n", videogame, hours_playing);
	return 0;
}
```


## C Functions

In C, functions HAVE to specify their type they return. Just like `int main() { }`

### Void

In C, the term `void` can be used within a function for 2 important reasons:

1: Explicitly saying that a function takes no arguments.

```c
int my_function(void) {
	return (int)(2 + 4)
}
```

2: Functions that don't return anything (including not an exit code since it wouldn't be a `main()`.)

```c
void my_function(int x) {
	printf("This is the %dth day of the week.", x);
}
```

## Math With C

- The `+` operator adds two numbers: `1 + 2` is `3`.
- The `/` operator divides two numbers, however:
    - if both numbers are integers, **integer division** is performed. The result will be an integer.
    - if either number is a float, **floating point division** is performed. The result will be a float.

See [[programming]], [[Backend]]

### Logical Operators C

Logical operators let you combine multiple conditions in C. There are three main logical operators you'll use all the time:

- `&&` – Logical `AND`: true if _both_ conditions are true
- `||` – Logical `OR`: true if _either_ condition is true
- `!` – Logical `NOT`: inverts a [[boolean]] value

### Ternary Operators C

Hard to explain.

`a > b ? 't' : 'f'` -> assign `t` or `f` depending on the outcome of the statement `a > b`