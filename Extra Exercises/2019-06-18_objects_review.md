# 2019-06-18 Objects Review

Copy the code below (all of it), read through, and complete the 3 missing parts. Each part is marked by a comment and is numbered.
**Ask questions** if you have any.

**READ ALL COMMENTS** especially if the comment is directly above a method - those usually explain what is expected from the method.

```
# A default Weapon
class Stick:
    base_dmg = 1
    def __init__(self, modifier):
        self.dmg = Stick.base_dmg + modifier
    
    def noise(self):
        print("Thwack! " + str(self.dmg) + " damage dealt")

#
# 1.) Define your own Weapon class like Stick but with a different base_dmg. 
# Make sure to have a constructor and noise method as well.
#

class Character:

    def __init__(self, name, health, weapon):
        self.name = name
        self.health = health
        self.weapon = weapon

    # subtracts the wielded weapons damage from the targets health
    def attack(self, target):
        #
        # 2.) complete me!
        # 
        self.weapon.noise()
        print(target.name + "'s health is now " + str(target.health))

    # returns a Boolean
    def isAlive(self):
        #
        # 3.) complete me!
        #

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


# 4.) Create 2 characters, arm one (or both) with your custom weapon, and have them battle it out!
```