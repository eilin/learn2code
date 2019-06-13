# Boolean Operations

But wait, what is boolean?

It just means "True or False".

Like numbers and strings, booleans are another data type that variables can hold.

In python, the "truthy" boolean is the "True" keyword and the "falsey" boolean is the "False" keyword.

```
is_quest_awesome = True

is_dm_being_mean = False
```

> BTW: truthy and falsey aren't strictly "real terms", but the meaning is clear and I think the words are funny to read.

# Truthy-Falsey Logic
Math has -+/* operations, and booleans have their own set of operations:
- and
- or
- ==
- not

To explain these, lets consider 3 variables _a_, _b_, and _b_

## and
<code>a = b and c</code>

_a_ will only be True if **both** _b_ and _c_ are both True. Otherwise _a_ is False.

## or
<code>a = b or c</code>

_a_ will be True if **either** _b_ or _c_ are True. Otherwise _a_ is False.

## ==
<code>a = b == c</code>

_a_ will only be True if the values of _b_ and _c_ are the same. Otherwise _a_ is False.

## not
<code>a = not b</code>

"not" just switches the value of whatever boolean it precedes. If _b_ is False, then _a_ will be assigned True, and vice-versa. 

You will also see the negation operator used in this form: <code>a = b != c</code>

You will need to use <code>!=</code> when comparing numbers.


> Do exercise 2 before moving on to the next lesson!