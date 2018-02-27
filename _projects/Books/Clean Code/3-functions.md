---
layout: note
level: 1
permalink: "/Books/CleanCode/3-functions/"
title: Functions
---

## Small

Functions should be **small**. Ideally, blocks within statements of _if_,
_else_, _while_, etc. should be one line long. Preferrably, that line should be a function call.
The extra benefit is that that function can have a nice descriptive name to make the code's purpose more readable.

General rule: the indent level of a function should not be greater than two or three.

**<span style="color: green">Encouraged</span>:** _at most_ 3 levels of indentation
{% highlight python %}
def f():
    for ...:
        if ...: 
   	    do_something()
    1   2   3
{% endhighlight %}

**<span style="color: red">Discouraged</span>:**
{% highlight python %}
def f():
    for ...:
    	if ...:
	   if ...:
	      do_something()
    1   2  3  4
{% endhighlight %}
Note the discouraged code contains 4 indentations from the function


## Do One Thing

__Functions should do one thing. Do that one thing well. Do it only__. To know if a function is doing more	than one thing, check if you can extract another function from it with a name that is not merely a
restatement of its implementation.

Note: If your function is divided into sections as declarations, initializations and algorithms, you may be doing more than one thing. Functions that do one thing cannot be easily divided into sections


## One Level of Abstraction per Function

Mixing levels of abstraction is confusing.

> __Step-Down Rule__: Code should read like a top-down narrative. That is, every function should be followed by
those at the next level of abstraction so we can read the program descending one level of abstraction at a time,
as we read down the list of functions (the facade at top , the details below).

Keeping functions to a single abstraction level is key to keeping functions short and making sure they do "one thing".

## Descriptive Names

The smaller a function, the easier it is to choose a descriptive name.
__Don't be afraid of making long names__. A long descriptive name is better than a long descriptive comment. Be consistent in choosing names by using the same phrases, nouns and verbs in the function names you choose.

## Function Arguments

The ideal number of arguments for a function is zero. Next is one, followed closely by two. Avoid ever having three arguments, whenever possible.

#### One-Argument Functions

Usually two reasons to pass a single argument and occasionally a third:

1. You want to ask a question about that argument. (e.g. boolean fileExists("my_file"))

2. You want to operate on that argument, transform it into something else and return it. (e.g. InputStream fileOpen("my_file"))

3. Occassionally we have single argument functions known as a  _events_ meant to interpret the function call as an event and use the argument to alter the state of the system. (e.g. void passwordAttemptFailedNtimes(int attempts))

Try to avoid one-argument functions that do not follow the above forms.

#### Three-Argument Functions

Are hard to understand because we have to worry about argument ordering.

#### Argument Objects

When a function needs more than two or three arguments, it's a sign that some arguments should be wrapped into a class of their own.
When groups of variables are passed together, they are likely part of a concept that deserves a name of its own.

#### Flag Arguments

Passing a boolean into a function is bad practice. Boolean arguments proclaim that this function does more than one thing. One thing if flag is true, and another if flag is false.

#### Verbs and Keywords

Good function names go a long way in showing the intent of a function and the order and intent of arguments.

Example, __one-argument functions should follow a verb/noun pair__. (e.g. writeField(name))

## Have No Side Effects

> __Function Side Effect__: When a function promises to do one thing, but also does other _hidden_ things.


## Command Query Seperation

Functions should either do something or answer something, but __not both__.
Either your function should change an object's state or it should return information about the object.

Suppose you have some function that alters an objects state and returns true if successful and false otherwise. The function is doing two things at once, specifically command and query. Example, 
{% highlight python %}
if (setUsername('username', 'billy')): ...
{% endhighlight %}
__set__ assigns a specified name to username if the specified name does not exist.
The solution is to seperate the command from the query.
{% highlight python %}
if (usernameExists('billy')):
   setUsername('billy')
{% endhighlight %}

## Prefer Exception to Returning Error Codes

#### Extract Try/Catch Blocks

Best to extract the bodies of the try and catch blocks out into functions of their own.

#### Error Handling is One thing
A function that handles errors should do nothing else. This implies if the keywordtry exists in a function, it should be the
very first word in the function and that there should be nothing after the catch blocks.
