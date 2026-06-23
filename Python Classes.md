
In python, classes are like a blueprint or template by assigning each "object" completely different features.

e.g:

```python
class Pokemon:
	name: "Pikachu"
	health: 100
```

This isn't a very safe way to do it as it doesn't stay for just that object and is "class-wide".

A better way is:

```python
class Pokemon:
	def __init__(self, name: str, health: int) -> None:
		self.name = name
		self.health = health
```

That allows you to do stuff like this:

```python
myPokemon = Pokemon(
	name="Pikachu",
	health=25
)

myNewPokemon = Pokemon(
	name="Charmander",
	health=123
)
```

And they share similar characteristics but are their very own objects.

## Methods

This is just functions in classes that don't only return data (don't even need to) but can edit the object's variables directly.

E.g:

```python
class Pokemon:
	def __init__(self, name: str, health: int) -> None:
		self.name = name
		self.health = health
	
	def give_health(self, health_amt: int) -> None:
		self.health += health_amt
		
		# no need to return data since it updates that objects' health directly 
```

## Invisible Values: (Encapsulation)

Just like the title shows, values that you don't want any developer editing can be hidden by using `__` before declaring the variable in the class. That means outside of class declaration the variable can't be used.

E.g:

```python
class Pokemon:
	def __init__(self, name: str, health: int) -> None:
		self.name = name
		self.health = health
		
		self.__damage_multiplier = 7
	
	def give_health(self, health_amt: int) -> None:
		self.health += health_amt
	
	def change_damage(self, damage: int) -> None:
		self.__damage_multiplier += damage
		# this works as it's still in class declaration

myPokemon = Pokemon(
	name="Pikachu"
	health=25
)

myPokemon.change_damage(5) # this will work as it's just calling a method

myPokemon.__damage_multiplier = 4 # this will NOT work as the value is private and it will raise an error
```


## Inheritance

So if you want multiple classes that are _kinda_ related to share similar values, you use inheritance.

```python
# main class
class Animal:
	def __init__(self, name, brain_power):
		self.brain_power = brain_power

# inherited class
class Dog(Animal):
	def __init__(self, name, brain_power, wl):
		super().__init__(brain_power)
		self.name = name
		self.woof_length = wf
		
# "Dog" shares the same "brain_power" data from Animal BUT doesn't share the same name as animal
```

## Polymorphism

"poly" -> many
"morph" -> form
"polymorphism" -> many forms

It's where child classes can have different stuff happen with methods named the same.

Here's a good example with Animals.

```python
# normal animal class (parent class)
class Animal:
	def __init__(self, name: str, life_span: float) -> None:
		self.name = name
		self.life_span = float(name)
	
	def speak():
		print("default animal speech")

# child class
class Dog(Animal):
	def __init__(self, name: str, life_span: float) -> None:
		super().__init__(name, life_span)
	
	def speak():
		print("woof!") # overriding normal class

class Cat(Animal):
	def __init__(self, name: str, life_span: float) -> None:
		super().__init__(name, life_span)
	
	def speak():
		print("meow!") # overriding normal class
```

Because you can declare the same method to do different things, some cool stuff can come from it.

```python
# code continued ..

animals [
	Dog(),
	Cat()
]

for animal in animals:
	animal.speak()
# would print
# woof!
# meow!
```

So that's cool.


See [[Python]]