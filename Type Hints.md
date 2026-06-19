
In [[Python]], type hints let you write function parameter type expectations.

```python

def add_number(num1: int, num2: int):
	# function goes here
	return num1 + num2
```

Also works for:

[[Lists]]
[[Arrays]]
[[Dictionaries]]

You can also use type hints for what the expected type will be returned with a function (good for code editor autocorrect.. and just remembering stuff)

```python
def add_number(num1: int, num2: int) -> int:
	# function goes here
	return num1 + num2
```

The `-> int` is the type hint for the `return` function.

## List / Set Hints

You can also add type hints to lists and sets.

```python
my_list: list[str] = ["the", "words", "and", "stuff"]
```

### Dictionary Hints

You can also do type hints to dictionaries by specifying type for key AND value.

e.g:

```python
# test scores example
students: dict[str, int] = {
	"Ben": 81,
	"Matthew": 95,
	"John": 88
}
```

### [[Tuple]] Hints

Tuples are fixed so each index of one actually has a meaning.

```python
item_stat: tuple[str, float] = ("Dogecoin", 0.57)
```