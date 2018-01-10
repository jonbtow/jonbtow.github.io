---
layout: note
level: 1
permalink: "/Books/CleanCode/3-functions/"
title: Functions
---

* ## Small

Functions should be **small**. This implies that blocks within statements for _if_,
_else_, _while_, etc. should ideally be one line long. Preferrably, that line should be a function call.
The extra benefit is that that function can have a nice descriptive name to make the code's purpose more readable.

General rule: the indent level of a function should not be greater than two or three.

**<span style="color: green">Encouraged</span>:** _at most_ 3 levels of indentation
{% highlight python %}
def f():
    for ...:
        if ...: 
   	    do_something()
{% endhighlight %}

**<span style="color: red">Discouraged</span>:**
{% highlight python %}
def f():
    for ...:
        if ...:
	   if ...:
	       do_something()
{% endhighlight %}
Note the discouraged code contains 4 indentations from the function


* ## Do One Thing

__Functions should do one thing. Do that one thing well. Do it only__. To know if a function is doing more	than one thing, check to see if you can extract another function from it with a name that is not merely a
restatement of its implementation.

Note: If your function is divided into sections as declarations, initializations and algorithms, you may be doing more than one thing. Functions that do one thing cannot be easily divided into sections

* ## One Level of Abstraction per Function

Mixing levels of abstraction is confusing.
__Step-Down Rule__: Want code to read like a top-down narrative. That is, every function should be followed by
those at the next level of abstraction so we can read the program descending one level of abstraction at a time,
as we read down the list of functions (the facade at top , the details below).