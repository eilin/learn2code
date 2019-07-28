# Iterating Through a List

It's time to come clean... this whole business of iterating through a list with using ```while index < len(my_list):``` is _not_ the usual Python way of doing it. I have purposefully taught the "hard" way of doing it so you can start with a more intuitive understanding of what's going on "under the hood"; that when you access an element in a list, you are **accessing an element at the i-th position offset from the start of the list**. 

Okay now let's go over the better way of doing this.

Let's go through a list of names of people in our party:

```
# Example 1
names = ['Scanlan', 'Grog', 'Pike', 'Vex']

for name in names:
    print("Hi I'm " + name)
```

_Boom_ it's that simple.

_"But hooooow?"_, I hear you screech and wail in confusion. Well go into more "under the hood" stuff in Part 2. Let's just go over the high-level usages of iterating through a list.

As you can see, ```in``` is a powerful keyword in Python. We've seen it used to check if a substring is part of a string:
```
name = 'Loyalist Guard'
if 'Guard' in name: # True
    ...
```

And now you see it in the context of lists, with the ```for``` keyword. The general syntax is as follows:
```
for some_object in my_list_of_objects:
    ...
```
And in each iteration of the loop, some_object will be the next object of your list - automatically set for you!

> Try out the new _for loop_ if you haven't already.

Alright, but what if you need the indexes of a list for some reason? There's a more pythonic way of doing that too. Take a look at this example where I print every other name in the party.

```
# Example 2
names = ['Scanlan', 'Grog', 'Pike', 'Vex']

for index in range(len(names)):
    if index % 2 == 0:
        print(names[index])
```
This will print 'Scanlan' and 'Pike'.

Let's take a look at that new function you haven't seen before, ```range(N)```.

```range(N)``` takes a number N as an argument and creates a list from 0 to N-1.

> Try it out in your interpreter: range(10)

```range``` actually can take a couple different arguments. You can specify a different start of your range instead of 0
```
range(4, 10) # [4, 5, 6, 7, 8, 9]
```
You can also specify a different "step amount" in your range. Check it out:
```
range(0, 10, 1) # same as range(10)
range(0, 10, 2) # [0, 2, 4, 6, 8]
```
In the example above, the 2nd call to ```range``` basically says "give me a list of all numbers starting at 0, increasing by 2, while still less than 10".

> Quick exercise: Rewrite example 2 above using the range function with 3 arguments
