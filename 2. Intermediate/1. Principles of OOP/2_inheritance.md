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

## Single vs Multiple Inheritance
What we saw above was _single inheritance_, where a child class has a single parent. We can also define a class to inherit from multiple parent classes.

```
class Creature:
    def __init__(self):
        self.status = 'normal'

class Undead(Creature):
    def poison_immune(self):
        if self.status == 'poisoned':
            self.status = 'normal'

class Mage(Creature):
    def cast_spell(self):
        print("magic missle pew pew pew")

class Lich(Undead, Mage):
    def raise_dead(self):
        print("RISE, MINIONS")

lich = Lich()

# show that poison_immune() works
lich.status = 'poisoned'
lich.poison_immune()
print(lich.status) # 'normal'

# show that cast_spell() works
lich.cast_spell()

# show that raise_dead() works
lich.raise_dead()

```

Multiple inheritance is a powerful way to reuse and combine existing classes.

## Overriding Parent Methods
Sometimes, we may want to use a method defined in the parent class but with some modifications in the child class.

For example, our Person class has a greet() method. We'll create a Guardsman class that inherits from Person, and we also want Guardsman to have a greet() method. However, I want the guard to say a greeting like a normal person _and_ say what he's doing. 

Heres how we can achieve this:

```
class Person:
    def __init__(self, name):
        self.name = name
    def greet(self):
        print("Hi I'm " + self.name)

class Guardsman(Person):
    def greet(self):
        super().greet()
        print("I'm patroling the city")

guard = Guardsman("Tamlin")
guard.greet()
```
This prints:
```
Hi I'm Tamlin
I'm patroling the city
```

The method ```super()``` gives you a reference to the parent class, so ```super().greet()``` is calling the greet method in Person.

If you tried doing this without super(), you'd ending up calling the greet method in Guardsman... which is definitely not what we want to happen here.

## Resolving Methods in Multiple Inheritance
You may have raised a question by now - if two parent classes define the same method, which method is run when it is invoked from the child class's object?

Reusing the Lich example from before, let's add a ```move()``` method to both parent classes and call ```lich.move()```.
```
class Creature:
    def __init__(self):
        self.status = 'normal'

class Undead(Creature):
    def move(self):
        print("lurches forward")
    def poison_immune(self):
        if self.status == 'poisoned':
            self.status = 'normal'

class Mage(Creature):
    def move(self):
        print("steps forward")
    def cast_spell(self):
        print("magic missle pew pew pew")

class Lich(Undead, Mage):
    def raise_dead(self):
        print("RISE, MINIONS")

lich = Lich()
lich.move()
```
Python resolves method calls in a specific order: First it looks for the method in the current class, then it goes in order (left to right) of the parent classes.

Here it checks for move() in Lich, then in Undead, then in Mage. Since it is first found in Undead, it uses the move() defined in Undead and prints "lurches forward"

> I actually don't know how to specify that how to run move() from Mage short of changing the inheritance order. Multiple inheritance can be a powerful tool, but also comes with it's own complexities - use with caution.