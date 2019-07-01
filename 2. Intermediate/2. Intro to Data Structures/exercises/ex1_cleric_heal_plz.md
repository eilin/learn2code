# Exercise 1: Cleric Heal PLZ kthxbai

The party is heavily wounded! Find who needs healing the most (has lowest health) and assign them to the 'heal_first' variable.

Feel free to change any part of the given code, except for the bottom part that checks your result.

```
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

party = [
    Character("Vex", 23),
    Character("Percy", 4),
    Character("Scanlan", 27),
    Character("Grog", 36),
    Character("Vax", 54),
    Character("Key", 30)
]

heal_first = None

index = 0
while index < len(party):
    # complete me!
    index += 1


# checks your answer
assert heal_first.name == 'Percy'
print("Correct!")
```