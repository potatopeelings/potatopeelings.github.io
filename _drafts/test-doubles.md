---
layout: post
title: Test Doubles - Dummy, Fake, Stub, Spy, Mock, Shim / Mole
tags: [ tools ]
---

When creating unit tests, it's usually easier to use external packages / libraries to help stub our dependencies. This post is a summary of the related .

### Terminology

#### SUT

System Under Test - the unit being tested.

#### Test Doubles

The generic term for anything that replaces the actual dependencies of the SUT (from [xUnit Test Patterns by Gerard Meszaros](
https://www.amazon.com/xUnit-Test-Patterns-Refactoring-Code/dp/0131495054))

In most cases, you just want your test double to provide specific data to the SUT during the test. At other times you don't want even that. Or you might want to record exactly how the SUT interacts with a dependency.

Accordingly, there are different kinds of Test Doubles

#### Dummy

Just fills a placeholder.

#### Fake

A fully functional replacement of the dependency (as far as the SUT is concerned). 

This can be anything from a sub-optimal but comprehensive alternative implementation of the dependency. Or something that covers all and only the functionality required by the SUT during the test.

#### Stub

A replacement for the dependency that allows you to control the exact values the SUT gets from the dependency during the test.

If your unit uses interfaces to interact with its dependencies and it's dependencies are injected, using a stub is as easy. Create a class that implements the interface and provides your test data and inject this new class instead of the dependency.

#### Shim

When a dependency cannot be replaced by a stub, you need to modify the dependency itself to make it provide the exact values you need the SUT to have during the test. The behaviour can be modified at run time or compile time.

Shims are used when you don't have the freedom to change how the SUT interacts with a dependency you want to control.

#### Spy

A stub that keeps track of how the SUT 

#### Mock

Advanced spying that keeps track of exactly how the SUT interacts with the dependency.

### Examples

Consider a chat bot that does 3 things
1. Greets the user formally
2. Asks them if they had a good night's sleep or good day at work (depending on the time)
3. Says bye informally

A sample interaction would go like this
```console
> Hi Michael.
> Did you have a good night's sleep?
> Bye Mike.
```

A C# implementation would probably have a 

```C#
using System;
					
public class Program
{
	public static void Main()
	{
		var bot = new Bot();

        bot.Greet();
        bot.Chat();
        bot.Close();
	}


    public class Bot()
    {
        public 
    }
}
```