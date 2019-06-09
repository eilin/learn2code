# Comparison Operations

Just two more operators to cover:
- <
- \>

Again, just like in math you can use these to compare numbers:

```
potion_price = 30

wallet = 50

can_afford = wallet > potion_price or wallet == potion_price
```

In fact, there's an easier way to write "greater than or equal to". We can rewrite the above example as:

```
can_afford = wallet >= potion_price
```

> The same goes for "less than or equal to", just use: <code><=</code>

Additionally, < and > can be used to compare more than just numbers. Comparing strings will compare by alphabetical. 

> You can compare other types as well... but we will not cover that here.