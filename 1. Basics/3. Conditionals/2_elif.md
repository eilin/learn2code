# else + if = elif

Nesting if-elses can get real ugly once there are too many levels. To keep things clean, python has **elif**

It's exactly what it sounds like, it combines 'else' and 'if' onto a single line and you don't need an extra level of indentation. Consider the following examples:

<code>
if statement1:<br>
&nbsp;&nbsp;#do thing<br>
else:<br>
&nbsp;&nbsp;if statement2:<br>
&nbsp;&nbsp;&nbsp;&nbsp;#do other thing<br>
&nbsp;&nbsp;else:<br>
&nbsp;&nbsp;&nbsp;&nbsp;if statement3:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#do other, other thing<br>
&nbsp;&nbsp;&nbsp;&nbsp;else:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#give up lol
</code>

And now look at the equivalent:

<code>
if statement1:<br>
&nbsp;&nbsp;#do thing<br>
elif statement2:<br>
&nbsp;&nbsp;#do other thing<br>
elif statement3:<br>
&nbsp;&nbsp;#do other, other thing<br>
else:<br>
&nbsp;&nbsp;#give up lol
</code>

Ah, isn't that better to read?