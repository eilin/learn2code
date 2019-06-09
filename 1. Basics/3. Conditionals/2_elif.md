# else + if = elif

Nesting if-elses can get real ugly once there are too many levels. To keep things clean, python has **elif**

It's exactly what it sounds like, it combines 'else' and 'if' onto a single line and you don't need an extra level of indentation. Consider the following examples:

```
if statement1:
  #do thing
else:
  if statement2:
    #do other thing
  else:
    if statement3:
      #do other, other thing
    else:
      #give up lol
```

And now look at the equivalent:

```
if statement1:
  #do thing
elif statement2:
  #do other thing
elif statement3:
  #do other, other thing
else:
  #give up lol
```

Ah, isn't that just cleaner? 