True or False.

It is 2 values, just True or False.

E.g: (Python)

```python
played_game = False # original state

print("Wanna play game now?")
answer = str(input("Yes or no"))

if answer.lower() in ["yes", "y", "yea", "yeah"]:
	played_game = True # boolean changed state
	print("Okay you have played game.")
```

Because there are only 2 states with a boolean, you can do cool stuff regarding