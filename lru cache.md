This is related to [[Higher Order Functions Python]], Functional Programming and [[Python]].

`lru cache` is a type of [[Memoization]] where computation results get cached up until a certain size, and once filled, the least called get replaced, so the most used remain in cache. It is a [[Python Decorators | decorator]].

In Python you can use it like this:

```python
from functools import lru_cache

@lru_cache()
def doubles(x: int) -> int:
	if x == 0:
		return 1
	return doubles(x - 1)
	
doubles(5) # nothing saved to cache, all computations necessary

doubles(8) # all computations up to 5 saved to cache, only the three after are needed

doubles(3) # already saved in cache, no computations needed

```



Also see: [[Closure Python]]