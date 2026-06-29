Enums is a sum type that is a _fixed set_ of pre-defined types. They are in replacement of strings and are more convenient.


## [[Python]] Enums:

In Python, you can go about using Enums by just importing the `Enum` module.

```python
from enum import Enum

Color = Enum("Color", ["RED", "BLUE", "GREEN"])


# now you can call it
print(Color.RED)
# will print Color.RED
```

### Match/Case
(Unrelated to Enums but have nowhere to put it.)

Cleaner way to put `if/else/elif` statements on fixed values (or _sum types_)

```python
from enum import Enum

class AgeGrade(Enum):
	COLLEGE = 16
	UNIVERSITY = 18
	JOB = 21

def get_color(color: str, ageGrade: AgeGrade):
	match (color, ageGrade):
		case ("red", ageGrade.COLLEGE):
			return 16
		case ("red", ageGrade.UNIVERSITY):
			return 18
		case ("blue", ageGrade.JOB):
			return 21
		
		
		case _:
			return 0
```
