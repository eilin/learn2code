# Classes and Objects

> This chapter might start off as confusing. Don't worry, and read on - the example should help a lot.

We've seen code that uses a number of variables to keep track of a character's attributes like name, health, class, strength, etc. Trying to use a separate variable for each character and attribute gets unwieldy quickly. 

It would be nice to be able to group these variables together and handle them all as one logical unit for each character. Such a collection is called an **object**.

But to create an object, we must first define its blueprint - the **class**.

Every object of the same class will have the same variable names, but each variable's value will be independent of other objects.

Confused? Looking at a real example will be much clearer.

## Defining a Class

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

> By convention, while variable names should be "snake_case", class names should be "CamelCase"

```
class Character:
  name = ''
  dnd_class = ''
  health = 0
```

> Notice how <code>class</code> is the keyword used to define the class, so I needed to use "dnd_class" to avoid a conflict with the keyword.

When we create a Character object, the default values for the variables will be the same as what we defined in the class (in this case, empty strings and 0).

> BTW we call the variables of a class/object **members**

Lets create an object for our character and set the members accordingly.

```
# Create an object by calling the class like a method
me = Character()

# Access a object's member using the .
me.name = "Derpachev"
me.dnd_class = "Gunslinger"
me.health = 80
```

Now imagine you have a function that needs many variables of a character as parameters. Instead of passing in all those variables separately, you can just pass in one object!

```
# Before
result = func(health, name, dnd_class, strength, armor, dex, gold, weapon_bonus)

# After
result = func(character)
```

## Members and Methods

As said before, the variables of a class are called **members**. Similiarly, any functions defined on a class are called **methods**.

Let's add a method to our Character class to introduce themself:

```
class Character:
  name = ''
  dnd_class = ''
  health = 0

  def greet(self):
    print("I am " + self.name + " the " + self.dnd_class)

```

We define a function like before, using **def**, but what is this "self" parameter?

> The following is an oversimplification, but it's true enough.

Objects store members and their values, but methods are stored in the Class. This is because while objects may have unique members, their methods will all be the same since they come from the same class.

So when you call a method on an object, the interpreter looks up the method on the class of the object.

In order to act on the members of the calling object, a **reference** to the object gets passed as the first argument to any method defined in a class - this reference is the "self" variable. If this reference was not passed in, the method in the class would have no idea which object is running it.

> Whew! That was a lot. Make sure that makes sense to you.