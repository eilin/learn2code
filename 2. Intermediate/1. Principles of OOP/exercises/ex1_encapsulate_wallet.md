# Encapsulate the Wallet
Let's practice the principle of encapsulation by rewriting this design of a Character class with a wallet.

```
class Character:
    max_wallet = 1000

    def __init__(self, name):
        self.name = name
        self.wallet = 0

    def pay(self, amount):
        if self.wallet < amount:
            print("I can't pay that!")
        else:
            self.wallet -= amount

    def add(self, amount):
        if self.wallet + amount > Character.max_wallet:
            print("I need a new wallet!")
        else:
            self.wallet += amount
```
As you can see, the logic and data for the wallet is all mixed in the Character. 
1. Clean it up by encapsulating wallet in it's own class.
2. Add a method to your Wallet class with the signature ```amount()``` that returns the current amount.

Use the following code to try out your solution:
```
merchant = Character("Thoren the Hat-Smith")
merchant.wallet.pay(10) # should print "I can't pay that!"
merchant.wallet.add(2000) # should print "I need a new wallet!"
merchant.wallet.add(50)
merchant.wallet.pay(20)
print(merchant.wallet.amount()) # should print "30"
```