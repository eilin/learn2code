# Polymorphism

## To Be Revisited
I need to clean up this lesson and add examples

### Skip this lesson until you've learned about Lists (Intro to Data Structures)

In my opinion, Python is not a good example to show the benefits of Polymorphism because the language is _dynamically_ typed. When you run ```my_obj.my_method()```, python doesn't care what "type" of object my_obj is - It just checks on-the-fly if my_obj has a method called "my_method". More importantly, it doesn't care what kind of objects you have in a list. If you loop through a list, calling "my_method" on all the objects, it will run without any complaints even if all the objects are of different classes.

In a _statically_ typed language like Java, before the code even runs it checks to see if the class of my_obj has a method called "my_method". Furthermore, objects in a list in Java all need to be of the same class - and yes, the Java compiler will check this before even running your code. TODO finish this