# Constructors

As said before, the variables of a class are called **members**. Similiarly, any functions defined on a class are called **methods**.

From the previous lesson, we learned that a 
special method called ```__init___``` serves as the constructor for the class, and that ```self``` must be the first parameter of the method. We can also add more parameters to the constructor to use during the initialization of new objects.

```
class DndCharacter:
    def __init__(self, name, dnd_class, health):
        self.name = name
        self.dnd_class = dnd_class
        self.health = health
```
We can also add logic in the constructor. Say we want to make sure that ```health``` is never initialized to be less than 0
```
class DndCharacter:
    def __init__(self, name, dnd_class, health):
        self.name = name
        self.dnd_class = dnd_class
        if health < 0:
            self.health = 0
        else:
            self.health = health
```
With this constructor defined, instead of writing 3 additional lines:
```
me = DndCharacter()
me.name = "Derpachev"
me.dnd_class = "Gunslinger"
me.health = 80
```
We can just write:
```
me = DndCharacter("Derpachev", "Gunslinger", 80)
```

> It's less typing and less reading. Win-win.