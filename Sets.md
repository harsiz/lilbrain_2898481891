In [[Python]], sets are much like [[Lists]] but they are unorderedand must be unique (no duplicate values.)

Sets use curly brackets (the ones [[Dictionaries]] user)

```python

cars = {"Honda Civic", "Lambo", "Bugatti"}

print(type(cars)) # will print set
```

Since dicts and sets share the same curly brackets, to define an empty set, you just use `set()`

Values can be added with `.add()`

Values can be removed with `.remove()`

## Set Mathematics

### Set Subtraction

You can remove all values from 2nd set from first set.

E.g:

```python
set_1 = {"cat", "dog", "salmon"}
set_2 = {"cat", "dog"}

set_3 = set_1 - set_2
```