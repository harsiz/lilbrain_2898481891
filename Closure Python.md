Similar to [[Higher Order Functions Python]] but it actually grabs an immutable variable type from outside its scope.

Example:

```python
from collections.abc import Callable

def example(initial_documents: list[str]) -> Callable[[str], [list[str]]]:
	my_top_variable = 2841
	
	def inner_function():
		nonlocal my_top_variable # this is what makes it available to be used in lower scope
		return my_top_variable + 4
	return inner_function()
```



See [[Python]], [[Recursion]]