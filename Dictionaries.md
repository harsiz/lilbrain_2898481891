A [[Python]] [[data structure]] that stores key-value pairs.

```python
my_dict = {
	"key": value,
	"key2": value2
}
```

Accessing a key that doesn't exist throws a `KeyError`. So instead of doing `my_dict["key3"]`, check first:

```python
if "key3" in my_dict:
	print("Exists!")
```

Or use `.get()` which returns `None` by default (or a fallback value) instead of crashing:

```python
my_dict.get("key3")         # None
my_dict.get("key3", "wow")  # "wow"
```

You can add or overwrite keys directly:

```python
my_dict["newkey"] = 123
```

Deleting a key:

```python
del my_dict["key"]
my_dict.pop("key")          # also returns the value
my_dict.pop("key", None)    # safe version, won't crash if missing
```

Looping:

```python
for key in my_dict:             # just keys
for key, val in my_dict.items() # both
```

Nested dicts are just dicts as values:

```python
my_dict = {
	"user": {
		"name": "harry",
		"age": 18
	}
}

my_dict["user"]["name"]  # "harry"
```

Dict comprehension (same as list comp but for dicts):

```python
squares = {n: n**2 for n in range(5)}
# {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

See also: [[Lists]], [[Python]]