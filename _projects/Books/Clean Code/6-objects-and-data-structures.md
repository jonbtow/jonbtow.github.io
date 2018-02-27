---
layout: note
level: 1
permalink: "/Books/CleanCode/6-objects-and-data-structures/"
title: Objects and Data Structure
---

## Data Abstraction
We do not want to expose the details of our data's implementation. Hiding the implentations of a data structure/objects is about abstractions. Exposing abstract interfaces allows users to manipulate the essence of the data without having to know its implementation.

## Data/Object Anti-Symmetry
__Objects (OOP)__ hide their data behind abstractions and expose functions that operate on that hidden data. This means that an object should not expose its internal structure through accessors because to do so is to expose, rather than hide, its internal structure.

__Data Structures (Procedural)__ expose their data and have no meaningful functions.

Dichotomy of objects and data structures:

> Procedural Code (code using data structures) makes it easy to add new functions without changing the existing data structures. Object Oriented code, on the other hand, makes it easy to add new classes without changing existing functions.

We can also say the complement:

> Procedural code makes it hard to add new data structures because all functions that work on the data must change. Object Oriented code makes it hard to add new functions because all classes must change.

In short, things that are hard for OO are easy for procedures and things that are hard for procedures are easy for OO.

_Note_: The idea that everything is an object is a myth because sometimes you want simple data structures with procedures operating on them.


## The Law of Demeter

The heuristic known as the Law of Demeter holds the idea that  __a module should not know about the innards of the objects it manipulates__. 

> __Law of Demeter__: A method _f_ of a class _C_ should only call the methods of,
-  C,
-  An object created by _f_,
-  An object passed as an argument to _f_,
-  An object held in an instance variable of _C_

<br> <br>Furthermore, _f_ should __not__ invoke methods on objects that are returned by any of the allowed functions ("talk to friends, not strangers"). This is why we should avoid code that chains method calls:

**<span style="color: red">Discouraged</span>:**
{% highlight python %}
outputDir = txt.getOptions().getBaseDir().getFullPath()
{% endhighlight %}

It is usually best to split up such chained calls as the one above if needed.
