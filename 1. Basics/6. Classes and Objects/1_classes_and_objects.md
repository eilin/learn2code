# Classes and Objects

> This chapter might start off as confusing. Don't worry, and read on - the example should help a lot.

We've seen code that uses a number of variables to keep track of a character's attributes like name, health, class, strength, etc. Trying to use a separate variable for each character and attribute gets unwieldy quickly. 

It would be nice to be able to group these variables together and handle them all as one logical unit for each character. Such a collection is called an **object**.

But to create an object, we must first define its blueprint - the **class**.

Every object of the same class will have the same variable names, but each variable's value will be independent of other objects.

Confused? Looking at a real example will be much clearer.

## The Simplest Example
Here's our class (blueprint) for a Person, creating an object of that class, and changing the name of that object.
```
class Person:
    def __init__(self):
        self.name = "no name"

me = Person()

me.name = "Percival"
```

So there's a few things to explain here.

### me = Person()
This line is creating an object of the Person class. You invoke the class name like it is a method, and the return value is a new object (or an instance) of that class.

### def \_\_init__(self):
This is defining a special method called <code>\_\_init__</code> , short for "initialize". Whenever an object is created, <code>\_\_init__</code> is invoked automatically by the computer.

> A method that is called automatically during object creation is generally referred to as a _Constructor_ in programming terms.

A constructor is usually used to set the initial values of the variables of the newly created object. In our example, the variable <code>name</code> is set to "no name".


### self
When we create an object in our example, <code>me = Person()</code>, we don't pass any arguments to the method. However, we see that the definition of <code>\_\_init__</code> takes an argument called "self" - what's going on?

> Alright, it's about to get a little weird

Methods defined on a class are available to all object instances of that class. When a class method is called, the computer needs some way to know which instance the method needs to act on. 

So all methods defined on a class must include <code>self</code> as the first parameter, and it is a reference to the object that is invoking the method.

This reference allows the computer to correctly apply the class method's effects to the object that is invoking the method.

> You may need to ask your instructor to draw out an example of what's going on.

### The . syntax
To access a variable or method of an object, you use a period between the object and the variable.

<code>me.name</code> accesses the variable <code>name</code> of the Person object assigned to the variable <code>me</code>.

> BTW we call the variables of an object "**members**"

## Another Example

Instead of organizing our characters like this:

```
my_name = "Derpachev"
my_class = "Gunslinger"
my_health = 80

scanlan_name = "Scanlan"
scanlan_class = "Bard"
scanlan_health = "60"
```

We'll define a Character class with variables for "name", "dnd_class", and "health":

> By convention, while member/method names should be "snake_case", class names should be "CamelCase"

```
class DndCharacter:
    def __init__(self):
        self.name = ''
        self.dnd_class = ''
        self.health = 0
```

> Notice how <code>class</code> is the keyword used to define the class, so I needed to use "dnd_class" to avoid a conflict with the keyword.

Lets create an object for our characters and set the members accordingly.

```
me = DndCharacter()
me.name = "Derpachev"
me.dnd_class = "Gunslinger"
me.health = 80

scanlan = DndCharacter()
scanlan.name = "Scanlan"
scanlan.dnd_class = "Bard"
scanlan.health = 60
```
Now when we need to use a method that uses these characters, instead of needing to pass in 6 variables, I can just pass in my character objects.

```
# Before
result = do_something(my_name, my_class, my_health, scanlan_name, scanlan_class, scanlan_health)

# After
result = do_something(me, scanlan)
```

> The more parameters a method takes the more likely you'll make a mistake when passing in arguments. In general, more concise code is simpler to read and write.
