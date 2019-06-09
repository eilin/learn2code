# Constructors

There are some special methods that you can define in a class, one of which is the **constructor**.

The constructor method name is ```__init__```

> That's 2 underscores before and after.

The constructor is called on an object when it is created, and is useful for initializing members. You can define any number of parameters, but like any other method the **self** reference is the first argument.

```
class Character:
  name = ''

  def __init__(self, name):
    self.name = name

```

> Note that you can name "self" anything since it's just another variable name, but for convention's sake (again) you should keep it as "self".