# Methods / Functions

> Before we start, I want to point out that while _technically_ methods and functions are different things, most of the programming world will understand if you use the terms interchangeably. The distinction will be covered in a later chapter. I too will be using the terms loosely and may switch between them.

Again, lets look at math - the granddaddy of programming - to explain this term. 

In math, **function notation** expresses an equation like <code>y = 2x - 2</code> as <code>f(x) = 2x - 2</code>

With function notation, you can easily express complicated equations with multiple functions. Remember seeing something like this in Algebra?

<code>a = f(x) - g(x) + s(t(x))</code>

Well, similiarly in code, we can express multiple lines of code if we define it inside of a _function_.

Imagine we need <code>2x - 2</code> a bunch of times in our code, and we need to solve for many different values of x. We can write the following function:

```
def f(x):
  return 2 * x - 2
```
And now whenever we need it, we just do:

```
# assume a,b,c are already defined
x = f(a)
y = f(b)
z = f(c)
```

## What's all this?
**def** is a keyword used to define functions. It is followed by the function's name, "f" in this case, and parentheses. Inside the parentheses are variables that we will pass to the function as **parameters**. Following the colon, starting on the next line and indented one level, is the code that will run everytime you call the function.

> parameters/arguments is another one of those words that will be used interchangeably. It just means what we are giving to the function (or _passing_ to the function) for it to use.

When we use the keyword **return**, the function returns whatever value is evaluated on that line.

> **arguments** and **return** are not mandatory in a function definition.

## Okay but why?
Number 1 reason: **reusability**. You don't want to have to copy-paste the same code over and over again just to use it more than once.

Here's some code that checks if an attack hits Scanlan and his health afterwards:

```
if monster_attack > scanlan_armor:
  return scanlan_health - monster_dmg
else:
  # Missed, no change
  return scanlan_health
```

But I want to reuse this code for everyone, so let's refactor this into a function:

```
def health_after_attack(health, armor, attacker_atk, attacker_dmg):
  if attacker_atk > armor:
    return health - attacker_dmg
  else:
    return health
```

And now we can reuse it like so:

```
scanlan_health = health_after_attack(scanlan_health, scanlan_armor, goblin_atk, goblin_dmg)

vax_health = health_after_attack(vax_health, vax_armor, troll_atk, troll_dmg)

percy_health = health_after_attack(percy_health, percy_armor, giant_atk, giant_dmg)

...

```

You can see how useful defining your own functions will be.

There are a large number of already available functions defined in the python standard library.

> We've already seen a standard library function before: **print()**!

And there are even more available in different packages that other people have published that you can import to use in your own project, but that is a topic for another time.