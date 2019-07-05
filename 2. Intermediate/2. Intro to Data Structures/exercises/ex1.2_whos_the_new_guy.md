# Exercise 1.2: Who's the New Guy

We have a list of names of people in our party and new member's names are always added to the end of the list. 

Write a method to return the last element of the list. If there is no one in the party, return None.

```
party = []

def get_new_guy(party):
    # complete me
```

Use the following code to test your solution
```
# test 1: empty list
assert None == get_new_guy(party)

# test 2: add 1 name
party.append("Abby")
assert "Abby" == get_new_guy(party)

# test 3: add multiple names
party.append("Broseph")
party.append("Charlotte")
assert "Charlotte" == get_new_guy(party)

print("All tests pass")
```

