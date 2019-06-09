# If, Else

> Starting with this chapter and for the following lessons and exercises, it is recommended to start writing code in a script instead of in the interactive console.

Sometimes we need our program to be able to behave differently based on the current state of its variables. To achieve this, we have what are called _conditional_ statements.

For example, when we encounter a monster we may want to fight or run depending on our current health. If our health is high, we fight. Else, we run. We can implement this as:

```
if my_health >= 50:
  # I have plenty of health
  print('fight!')
else:
  # My health is low
  print('run!')
  ```

> **Woah nelly!** Why are there **hashtags** in my code? Anything after a pound symbol is a _comment_. Comments are ignored by the interpreter, and we can use them to write for ourselves what code is doing or why it's doing it. Expect to see comments being used in following examples where I want to show code happening but don't actually want to write it out.

Note that not every 'if' statement needs an 'else', but every 'else' needs an 'if'. Here's an example of an 'if' without an 'else':

```
grog_dmg = strength + weapon_bonus

if is_raging:
  grog_dmg = grog_dmg + rage_bonus

monster_health = monster_health - grog_dmg
```

## Indentation
You may notice that the print statments are indented, compared to the if and else lines. This is actually mandatory in python! Indentation lets the interpreter know which 'block' of code should be run when then 'if' statment is true, and which 'block' to run for the 'else'. 

Even if it wasn't mandatory, like in other languages, you should still indent code to make it easier to see where it block begins and ends.

> You can use spaces OR tabs to indent. Incidentally, it's a meme to treat the tabs vs spaces debate as a holy war.

The _number_ of spaces/tabs doesn't matter as long as it's the same throughout the block.

## Nesting Conditionals

When your logic gets more complicated, you'll find yourself needing more if-elses, and if-elses inside your if-elses.

The same rules apply as before, just one indentation level deeper than the previous level.

Imagine you want to want to sneak by a guard to steal some gold, or failing that to try to talk your way past him and swipe a fraction of the loot, or failing all that to run away.

```
if stealth_check > guard_perception:
  # snuck past, steal all of it!
  my_gold = my_gold + treasure
else:
  if deception_check > guard_wisdom:
    # bluffed my way in, grab a handful
    my_gold = my_gold + treasure / 10
  else:
    print('run for it!')
```
