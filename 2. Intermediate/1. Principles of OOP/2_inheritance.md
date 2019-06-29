# Inheritance

The main benefit of inheritance is to reduce duplicate code between similar Classes.

We've seen separate classes for Characters and Monster in a previous exercise.

```
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def attack(self, target):
        print(self.name + " attacks " + target.name)

    def greet(self):
        print("I am " + self.name)

class Monster:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def attack(self, target):
        print(self.name + " attacks " + target.name)

    def greet(self):
        print("Rawr!")
```

These classes have a lot in common - the constructor and attack methods do the same thing. What we can do is create a __base class__ with these methods that both Character and Monster __inherit__ from.

Another term for a base class is a __parent__ class, and we say that classes that inherit from a parent is a __child__ class of that parent.

For this example, we'll create a parent class called Creature and have Character and Monster be child classes of Creature.

```
class Creature:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def attack(self, target):
        print(self.name + " attacks " + target.name)

class Character(Creature):
    def greet(self):
        print("I am " + self.name)

class Monster(Creature):
    def greet(self):
        print("Rawr!")
```
You'll notice that the definition of Character and Monster has changed a little: the parentheses after the class name denotes that the parent class is Creature.

Now you can use any method/member declared in the parent class from the child. See the below example:

```
c = Character("warlock", 70)
m = Monster("lion", 20)

c.attack(m)
m.attack(c)
```

As you can see, the constructor and attack methods are still available in both classes - and only defined once in the parent!

# Conclusion
The priciple of inheritance defines parent/child relations between classes, allowing child classes to use code defined in the parent.