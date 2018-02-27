---
layout: note
level: 1
permalink: "/Books/CleanCode/5-formatting/"
title: Formatting
---

Formatting is important. Code formatting is about communication, and communication is the professional developer's first order of business (not "getting it working").


## Vertical Formatting
How big should a source file be?
_Clean Code_ suggests java class files should be typically 200 lines long with an upper limit of 500.

#### Newspaper Metaphor
Source files should be like a newspaper article. The name should be simple but explanatory and should be enough to tell us if we're in the right module.
The topmost parts of the source file should provide the high-level concepts and algorithms. Detail should increase as we move downward until the end where we find the lowest level functions and details.

A newspaper is composed of many articles; most are very small. Very few contain as much text as a page can hold. This makes the newspaper usable. If the newspaper were just one long story of facts, dates, and names, we wouldn't read it.

#### Vertical Opennes Between Concepts
Each line represents an expression or a clause and each group of liens represents a complete thought. __Thoughts should be separated from each other with blank lines__.

Each blank line is a visual cue that identifies a new and separate concept.

#### Visual Density

If opennes separates concepts then vertical density implies close association. Lines of code that tightly related should appear vertically dense.

#### Vertical Distance
Concepts that are closley related should be kept vertically close to each other and should not be separated into different files unless you have a very good reason (this is one of the reasons that protected variables should be avoided).

#### Vertical Declarations
Variables should be declared as close to their usage as possible.
Because our functions are very short, local variables should appear at the top of each function. Control variables for loops should be declared within the loop statement or just before a loop in rare cases.

__Instance Variables__ should be declared in one well known place either it be at the top of the class (like java) or the bottom (like c++).

#### Dependent Functions
If one functions calls another, they should be vertically close, and the caller should be above the callee if possible.

#### Vertical Ordering

In general function call dependencies should  point in the downard direction, i.e. a function that is called should be below a function that does the calling.

As in newspaper articles, the most important concepts come first and we expect them to be expressed with the least amount of detail. This allows us to skim source files, getting the gist from the first few functions without having to immerse ourselves in the details.

## Horizontal Formating
How wide should a line be? According to the Clean Code lines should be kept to 80 characters. It is good to keep to a hard limit on 120 in rare cases you need more than 80.

#### Horizontal Openness and Density
Use horizontal white space to associate things that are strongly related and disassociate things that are more weakly related.
(e.g. assignments have two distinct and major elements the left and rigth side; spaces accentuate this)

#### Indentation
A source file is a hierarchy rather like an outline. Each level of the hierarchy is a scope into which names can be declared and in which declarations and executables are interpreted. Indent lines of code in proportion to their position in the hierarchy.

__Breaking Indentation__. It is sometimes tempting to break the indendation rule for short _if_statements or functions. Prefer not doing this.

## Team Rules
A team of developers should agree upon a single formatting style, and then every member of that team should use that style. Software should have consistent style rather than look like it was written by a bunch of disagreeing individuals.
