# Basic Review
2019-06-12

## Exercise 1
Here is a piece of code that has been started. It defines a method called "roll_die" which simulates rolling a single dice. This method will print out the result of it's roll so you can see what's happening.

Your task is to finish implementing the method "roll_dice", which simulates rolling multiple dice and returns the sum of the rolled numbers.

Use "roll_die" in your implementation of "roll_dice".

```
import random

# Simulates rolling a single dice.
# For example, roll_die(20) simulates rolling 1d20
def roll_die(dice_sides):
  roll = random.randint(1, dice_sides)
  print(roll)
  return roll

# Simulates rolling multiple dice.
# For example, roll_dice(2, 10) simulates rolling 2d10
def roll_dice(n, dice_sides):
  total = 0
  # complete me!
  return total


# Use this to test your implementation
roll_total = roll_dice(2, 10)
print("I rolled a total of:")
print(roll_total)

```

## Exercise 2
Rogues determine the number of dice they roll for their sneak attack based on their level.

We'll use a simplified version of their level/dice relationship for this exercise.
```
Level | Dice
------+------
  1   |  1   
  2   |  1   
  3   |  2   
  4   |  2   
  5   |  3   
  6   |  3  
  7   |  4   
  8   |  4   
  9   |  5   
```

Write a method that, given a rogue's level, returns the number of dice to roll for their sneak attack.

```
def dice_for_sneak_atk(level):
  # complete me!

# Use this code to test your method
level = 1
while level < 10:
  print(dice_for_sneak_atk(level))
  level += 1
```

There are multiple ways to do exercise 2, such as writing an "if" check for every level in the table. 

> Challenge: Once you have it working, see if you can complete it using only 4 "if"s

> Challenge: Try to think of how to do it without any "or"s

## Exercise 3
You've gotten this far - great!

Now use the methods you just completed to figure out how many D6s to roll for a level L rogue's sneak attack (you decide the level), then roll the dice and see what your how much damage your sneak attack deals.