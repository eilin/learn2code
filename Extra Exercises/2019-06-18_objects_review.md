# 2019-06-18 Objects Review

Copy the code below (all of it), read through, and complete the missing parts.
**Ask questions** if you have any.

```
# A default Weapon
class Stick:
    dmg = 1

#
# define your own Weapon class, make sure it has a "dmg" member variable
#

class Character:
    name = 'no name'
    weapon = Stick()
    health = 0

    def __init__(self, name, health):
        self.name = name
        self.health = health

    # subtracts the wielded weapons damage from the targets health
    def attack(self, target):
        # complete me!
        print(target.name + "'s health is " + str(target.health))

    # returns a Boolean
    def isAlive(self):
        # complete me!


def battle(char1, char2):
    print("The battle begins!")
    while char1.isAlive() and char2.isAlive():
        char1.attack(char2)
        if char2.isAlive():
            char2.attack(char1)
    print("The battle is over!")
    if char1.isAlive():
        print(char1.name + " wins!")
    else:
        print(char2.name + " wins!")


# create 2 characters, arm one with your custom weapon, and have them battle it out!
```