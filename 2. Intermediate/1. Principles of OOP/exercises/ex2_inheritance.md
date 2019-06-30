# Inheritance

Below are dummy definitions of various DnD classes. Above each one is a comment that denotes the method(s) that should be available on the class. Some methods are unique to a specific class, but other methods are common between multiple classes.

Furthermore, every class should have the member "name" and a "greet()" method.

It is your job to design the inheritance relations between the different classes in order to minimize the amount of code you need to write.

Whiteboard your design with your instructor before coding, and feel free to add any more parent classes that you need.

```
# duel(), rage()
class Barbarian:
    pass

# duel()
class Fighter:
    pass

# duel(), heal(), smite()
class Paladin:
    pass

# heal()
class Cleric:
    pass

# cast(), invoke_patron()
class Warlock:
    pass

# cast(), metamagic()
class Sorcerer:
    pass

# cast(), heal(), cast_ritual()
class Druid:
    pass

# cast(), duel(), hunt()
class Ranger:
    pass
```

Use the code below to check if everything works as expected

```
b = Barbarian("Blug")
b.greet()
b.duel()
b.rage()

f = Fighter("Fiona")
f.greet()
f.duel()

p = Paladin("Peluvitar")
p.greet()
p.duel()
p.smite()
p.heal()

c = Cleric("Crimdor")
c.greet()
c.heal()

w = Warlock("Wurmtongue")
w.greet()
w.cast()
w.invoke_patron()

s = Sorcerer("Staal")
s.greet()
s.cast()
s.metamagic()

d = Druid("Diviciacus")
d.greet()
d.cast()
d.cast_ritual()
d.heal()

r = Ranger("Roamwind")
r.greet()
r.duel()
r.cast()
r.hunt()
```
Here's the expected output, but feel free to change the phrases they say:
```
I'm Blug
I start a duel!
I start to RAAAAGE!
I'm Fiona
I start a duel!
I'm Peluvitar
I start a duel!
I SMITE MY FOE
I heal my party!
I'm Crimdor
I heal my party!
I'm Wurmtongue
I cast a spell!
I call upon my patron's power!
I'm Staal
I cast a spell!
I bend magic to my will!
I'm Diviciacus
I cast a spell!
I cast a spell as a ritual!
I heal my party!
I'm Roamwind
I start a duel!
I cast a spell!
I hunt my enemy...
```