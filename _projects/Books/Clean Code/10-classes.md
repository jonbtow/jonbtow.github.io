---
layout: note
level: 1
permalink: "/Books/CleanCode/10-classes/"
title: Classes
---

## Class Organization

## Encapsulation
Like to keep variables and utility functions private, but do not be fanatic about it, though loosening encapsulation is always a last resort.

## Classes Should Be Small!
Smaller is the primary rule when it comes to designing classes.

How small? In function we measure size by physical lines. With classes we count _responsibilities_. Responsibilities are the things a class has to deal with.

The name of a class should describe what responsibilities it fills and can help determine class size. If you can't derive a concise name for a class then it's likely too large.


## Single Responsibility Principle (SRP)

> __SRP__: A class or module should have one, and only one, reason to change (one responsibility). i.e. one reason to be rewritten.

SRP gives us both a definition and responsibility, and a guideline for class size.

Trying to find responsibilities (reasons to change) helps us recognize better abstractions in our code.

__Example__: Consider a module that compiles and prints a report. Imagine such a module can be changed for two reasons. First, the content of the report could change. Second, the format of the report could change. These two things change for very different causes; one substantive, and one cosmetic. The single responsibility principle says that these two aspects of the problem are really two separate responsibilities, and should therefore be in separate classes or modules.

Every sizable system will contain a large amount of logic and complexity but the primary goal in managing such complexity is to _organize_ it so that a developer knows where to look to find things and need only understand the directly affected complexity at any given time.

Summary: We want the system to be composed of many small classes, not a few large ones. Each small class encapsulates a single responsibility, has a single reason to change, and collaborates with a few others to achieve the desired system behaviors.

## Cohesion

Classes should have a small number of instance variables.

In general, the more variables a method manipulates the more cohesive that method is to its class.
__Want cohesion to be high__. High cohesion means that methods and variables of the class are
co-dependent and hang together as a logical whole.
