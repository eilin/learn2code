# List

> I was planning a big "deep-dive" lesson on Lists, but decided to save it for later. Here instead is a much more straight-forward introduction to Lists.

Lists! This is a special class built-in into Python. It is a handy way to organize a group of objects, especially if the number of objects in the group changes.

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

## Accessing Elements in the List
Right now, our party_members list looks like:
```
['percy', 'grog', 'vex', 'vax', 'scanlan', 'key']
```
_Element_ is just a fancy term for "item in our list". If we want to get the first element, we do:
```
element = party_members[0]
print(element) # 'percy'
```
> "Wait, what, why?" I hear you ask

The bracket notation for accessing elements is mostly "historical" reasons, I think. Lists in earlier programming languages used [] so Python followed suit. As for the '0', it makes sense when you consider how this "translates" to the computer:

When you write ```my_list[k]```, it tells the computer "I want to access the k-th element from the beginning of my_list".

So here's your party_member list drawn out with the _index_ of each element numbered below:
```
+-------+-------+------+---
|'percy'| 'grog'| 'vex'| ...
+-------+-------+------+---
    0       1       2    
```