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

