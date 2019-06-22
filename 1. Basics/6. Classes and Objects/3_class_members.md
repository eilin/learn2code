# Class Members

So far, all variables we've seen defined in a class are called **instance members** on a technical level.

```
class Person:
    def __init__(self, name):
        self.name = name # this is an instance member
```

Any variable defined on ```self``` is an instance member.

We call it that because the value of the member is dependent on the instance (object) of the class that we are referring to.

```
a = Person("Abby")
b = Person("Bron")

p = a
print(p.name) # prints Abby

p = b
print(p.name) # prints Bron
```

We access ```p.name``` twice and we get two different names because we reassign ```p``` to point to a different instance before accessing ```name``` the second time.

Now we understand instance members, we can discuss **class members**.

Whereas instance members are independent of other objects, class members are shared between all objects of the same class.

Lets say that all People are the same race.
So instead of adding a ```race``` member to every object instance, lets just put one ```race``` member on the class.

```
class Person:
    race = "Human" # class member
    def __init__(self, name):
        self.name = name # instance member

    def greet(self):
        print("I am " + self.name + " the " + Person.race)
```
Both objects ```a``` and ```b``` have will have access to ```race```.

Now lets look at what happens when we modify a class member:

```
a = Person("Abby")
b = Person("Bron")

a.greet() # prints "I am Abby the Human"
b.greet() # prints "I am Bron the Human"

Person.race = "Elf"

a.greet() # prints "I am Abby the Elf"
b.greet() # prints "I am Bron the Elf"

```
As you can see, the change to the shared class member is reflected in both instances of the class.

Class members are useful when you need to be able to share some state/value across all instances of that class. In other programming languages, this type of variable is called a _static_ member.

## Accessing Class Members from Instances
We've seen that we can access class members using the syntax of ```ClassName.class_member``` but we can also do ```object.class_member```. See the below example.

```
a = Person("Abby")
print(a.race) # prints Human
```

But now what do you think this prints?
> Alright, here gets _weird_.

```
a = Person("Abby")
b = Person("Bron")

print(Person.race)
print(a.race)
print(b.race)

a.race = "Gnome"

print(Person.race)
print(a.race)
print(b.race)
```

Take a guess before running it for yourself.

Did you expect it would print the following?
```
Human
Human
Human
Gnome
Gnome
Gnome
```

But it actually prints this!
```
Human
Human
Human
Human
Gnome
Human
```
What's actually going on is that when you access a member of an object and it only exists as a class member, a instance member is created on the object with a default value of the class member. So modifying ```a.race``` is actually modifying the instance member on ```a``` instead of the class member.

