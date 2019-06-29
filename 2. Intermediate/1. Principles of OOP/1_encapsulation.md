# Encapsulation

We've basically covered this already in our introduction to Classes and Objects - with the motivation of being able to group "character" related variables together, we created a Character class to treat a collection of related variables as a single unit to describe a particular character.
Additionally in the Character class we defined methods that act upon the members of the object, such as ```take_damage()```, ```is_alive()```, and ```greet()```.

The basic definition of encapsulation is __to bundle related data and behaviors together__.

The full definition goes a step further: encapsulation also includes the notion of __restricting direct access to certain members/methods__.

For example, some languages have _access modifiers_ that restrict access of a object's members to usages within the object itself.

Here's an example of access modifiers in Java. (Don't worry about understanding it 100%)
```
// Java comments use "//" instead of "#"
class Character {
    public String name; // defines name as a String
    private int health; // defines health as an integer

    public void setHealth(int h) { // "void" means return nothing
        this.health = h; // "this" is like Python's "self"
    }

    public int getHealth() {
        return this.health;
    }
}

Character c = new Character();
c.name = "Lord Zymeth"; // Ok
c.health = 100; // Error!
c.setHealth(100); // Ok
```

Why are access modifiers beneficial? Imagine a complicated class that simulates a full battle between a character and enemy. There's a method called ```fight``` that starts the fight, and a whole bunch of other methods that are used to simulate the action.
```
class Battle:
    def __init__(self, character, enemy):
        ...
    def fight(self):
        ...
    def determine_next_action(self, fighter):
        ...
    def execute_action(self, fighter, action, target):
        ...
    def is_fight_resolved(self):
        ...
    ...
    
```
Now when the next programmer comes along to use your code (or yourself, a week later), it's hard to see which methods are intended for use outside the class.

In Java, you'd mark ```fight``` as public and everything else as private. Then it's very clear which methods shouldn't be touched from outside the class.

In Python there's no explicit "private" modifier, but there is a convention you can follow: any members/methods that start with "_" is understood to be "private".

```
class Battle:
    def __init__(self, character, enemy):
        ...
    def fight(self):
        ...
    def _determine_next_action(self, fighter):
        ...
    ...
```
Now the next programmer to read your code will think "Ah, I shouldn't call ```_determine_next_action``` myself - otherwise I risk messing up the state of the Battle object".

## Conclusion

The principle of encapsulation groups related data and behaviors together as a single entity and restricts access members/methods to hide implementation details.