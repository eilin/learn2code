# The While Loop

Like conditionals, loops provide control over the logical path the program takes through your code. If you need something to run multiple times, you need a loop.

Here's the basic syntax:
```
condition = True

while condition:
  # execute your code here
```

If <code>condition</code> never changes to False, the loop will continue forever and the program will never exit!

Here's another example, where we only want the loop to run 10 times:

```
count = 0

while count < 10:
  # execute your code here
  count = count + 1
```

> You can try this out: just replace the comment with <code>print(count)</code>

Let's see another, slightly more interesting, example. Let's see how many rolls it takes for us to get a nat20.

> 'random' is a python module that we can import and use. Remember how I mentioned importing earlier?

```
import random

got_20 = False
rolls = 0

while not got_20:
  # this calls the randint method from the random module,
  # and gets a random integer between 1 and 20
  roll = random.randint(1, 20)
  rolls = rolls + 1
  if roll == 20:
    print('natural 20!')
    got_20 = True

print(rolls)

```