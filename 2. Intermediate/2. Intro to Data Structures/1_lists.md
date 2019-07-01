# List

Up to this point, you may have wondered how to write code that handles a dynamic number of objects - after all, you can't manually declare a new variable for every new object you may need in your program. 

A List is a special class built-in into Python and provides a simple way to organize multiple objects.

> I was planning a big "deep-dive" lesson on Lists, but decided to save it for later. Here instead is a much more straight-forward introduction to Lists.


## Creation
You can create a list in 2 ways:

1. Use the class-name constructor:
```
my_list = list() # for whatever reason, they made the class name lowercase.
```

2. Use the bracket notation:
```
my_list = []
```

Both of these are the same, it creates a new empty list.

## Initializing the List
If you already have objects before you create your list, you can initialize your list with these objects by using the bracket notation.
```
p = "percy"
g = "grog"
v = "vex"
party_members = [p, g, v]
```
> Side-note: yep, Strings are objects. Supriiise

## Adding to the List
After your list is created, you can add more objects by using the ```append()``` method:
```
party_members.append("vax")
party_members.append("scanlan")
party_members.append("key")
```
> for you non-languagers, "append" means "add-on-to". It's easy to remember that ```append(v)``` adds v onto the end of your list.

## Accessing Elements in the List
Right now, our party_members list looks like:
```
['percy', 'grog', 'vex', 'vax', 'scanlan', 'key']
```
_Element_ is just a fancy term for "item in our list". If we want to get the first element, we do:
```
p = party_members[0]
print(p) # 'percy'  
```
> "Wait, what, why?" I hear you ask

The bracket notation for accessing elements is mostly "historical" reasons, I think. Lists in earlier programming languages used [] so Python followed suit. As for the '0', it makes sense when you consider how this "translates" to the computer:

When you write ```my_list[k]```, it tells the computer "I want to access the k-th element from the beginning of my_list".

So here's your party_members list drawn out with the _index_ of each element numbered below:
```
+-------+-------+------+---
|'percy'| 'grog'| 'vex'| ... and so on
+-------+-------+------+---
    0       1       2    
```

> The number that refers to the position of an element is often called the "index", you will see plenty of variations of ```my_list[index]``` or ```my_list[i]```

So if you write ```my_list[2]```, the computer reads it as "give me the element that is 2 spaces over from the beginning".

> Perception Check: what is the value of ```party_members[2]``` in the above example?

## Removing Elements from a List
If you no longer need an object in a list, you can call ```remove(v)```, and the list will remove the first element that matches the ```v``` you pass in. 

```
# uh oh percy is deadsies
party_members.remove('percy')
```

## Final Notes
There are other useful methods built into Lists, but here are two helpful methods built into the language:
- len(my_list) # built in method that returns the length of the list (number of elements)
- print(my_list) # will print the list in an easy to read format

And here's a basic way to iterate through a list:
```
index = 0
while index < len(my_list):
    print(my_list[index])
    index += 1
```
There's a better/simpler way too, but we'll cover that after you understand Lists well enough.
