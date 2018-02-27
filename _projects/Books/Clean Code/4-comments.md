---
layout: note
level: 1
permalink: "/Books/CleanCode/4-comments/"
title: Comments
---

Comments are always failures. They compensate for failing to express ourself in
code. Code changes, so the longer a comment exists and the farther away it is from the code it describes,
the more likely it is be wrong.

Truth can only be found in one place: the code. Only the code can tell you what it does.

## Comments Do Not Make Up for Bad Code
Rather than spend time writing comments explaining messy code, spend it cleaning the mess.

## Explain Yourself in Code
Most of the time you can write a function that says the same thing as the comment you want to write.

**<span style="color: red;">Discouraged</span>:**
{% highlight python %}
# check to see the viewer is old enough to see PG-13 Movie
if (viewer.age > 13 || (viwer.age <= 13 && viewer.accompanied))
{% endhighlight %}

**<span style="color: green;">Encouraged</span>:** explain in code
{% highlight python %}
if (viewer.isEligibleForPG13())
{% endhighlight %}


## Good Comments

#### Legal Comments
Sometimes corporate coding standards force certain comments for legal reasons (e.g. Copyright and authorship)
{% highlight python %}
# Copyright 2018 by ....
{% endhighlight %}

#### TODO Comments
TODOs are jobs that a programmer thinks should be done, for some reason couldnt be done at the moment. It is not an excuse to leave
bad code in the system. Note that TODO can be useful reminders.

#### Warning of Consequences

#### Amplification
A comment may be used to amplify the importance of a piece of code that may otherwise
seem inconsequential.