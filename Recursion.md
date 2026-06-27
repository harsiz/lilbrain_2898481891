It's something (as of 26/06/2026) I don't like much.

It is a function that returns itself. It is a type of [[Higher Order Functions Python]].

```python
def countdown(num: int) -> int:
	if num < 1:
		return num
	return countdown(num - 1) 
```

I don't like it because you can't recurse forever. There needs to be a conditional in place to prevent it from infinitely recursing.

See more: [[Python]]