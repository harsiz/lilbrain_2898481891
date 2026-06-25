To put it simply, _Lambda_ just means an anonymous function.

> _What does that mean?_

An anonymous function is just a regular function that does the thing and returns a value. It can never be recalled again without re-writing the entire function again.

Example:

```python
# Regular functions:

def double_num(num: int = 0) -> int:
	return num * 2
	
# Lambda function

lambda x: x * 2
print(x(4))
# 8
```

You can actually also use it for one-liners:

```python
age = 28
print((lambda x: x * 2)(age))
# 56
```
