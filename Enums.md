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