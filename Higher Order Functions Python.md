These are functions that take a callable (function) as an argument _or_ return a callable.

## map() function

The `map()` function is a _higher order_ function that takes 2 arguments:

- `function` (callable)
- `iterable` (list, tuple, set etc)

and returns an `Iterator` object with the function applied to all items in the iterable.

E.g:

```python

def double_nums(num: int) -> int:
	return num * 2


# map func speeds up loops
my_numbers = [1, 4, 6, 2, 5, 1, 5, 12, 5]


doubled_nums = map(double_nums, my_numbers)
doubled_nums = list(doubled_nums) # convert the Iterator obj into a usable list.
```

## filter() function

The `filter()` function (much like the `map()` function) is a _higher order_ function that returns an Iterator object (basically a list) of a function where all items in the iterable that were true.

E.g:

```python

def number_is_odd(num: int) -> int:
	return num % 2 != 0

numbers = [1, 4, 5, 2, 4, 8, 3]

new_numbers = list(filter(lambda x: number_is_odd(x), numbers))
# new_numbers will only return the numbers that satisfied the "number_is_odd" function.

```

See more [[Python]] , [[Python OOP]], [[Python Classes]]