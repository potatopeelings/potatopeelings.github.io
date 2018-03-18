---
layout: post
title: Inversion of Control
---

Inversion of Control (IoC) is a design *principle*.

Many *programming constructs* are based on this principle - event loops, frameworks and dependency injection to name a few. Each such construct replaces a traditional way of doing the same thing. Compared to the traditional way, the IoC way inverts the order in which control flows.

## Event Loops

Let's take a not-so-real-life example - we are a fire marshal in a town with one house. In Traditional town, we call up the owner to check if there is a fire. In Inversion of Control town, the owner calls us if there is a fire. This is basically an _event loop_ - instead of our program requesting the user for input and acting on it, a user triggers our event handler.

## Frameworks

A _framework_ is the IoC alternative to a program that uses library functions. Instead of our code calling the library functions, frameworks hand over control to our custom code.

## Dependency Injection

In _dependency injection_, the responsibility of creating a called object's dependencies shifts from the called object to whatever is calling it.

Inversion of Control is a catch all term for design patterns where the traditional control handover is reversed.
