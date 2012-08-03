---
layout: post
title: "Excel: Programming for Non-programmers"
date: 2012-08-02 23:00
comments: true
categories:
- Paradigms
- Reactive
- Functional
---

## Context
*I'll start by giving a bit of context on my work and my motivation in writing this article.*

#### Excel and My Day Job

I currently work in the IT department at a major North American transportation company; I pay the bills by writing a lot of Java and JavaScript.  I love programming and automating repetitive tasks; both for myself and for my users.  When my day job is done, I like hacking on various personal projects - mostly in Clojure.  

Within my employer's IT department, Excel is the ugly red-headed step child (not to disparage red-heads or adopted children).  Many of our users effectively run our business from Excel spreadsheets, and the software we are often asked to write is frequently a glorified, half-baked, monster of an Excel clone ... running in a JEE container with JSPs serving up the UI.  My understanding is that this is a common experience in "Enterprise IT".

A couple of years ago, a co-worker of mine made this very observation, and jokingly stated that we should quit writing software and just give our users Excel for everything.  We had a good laugh, but for some reason I couldn't stop noticing how effective non-programmers are with Excel.

As I've continued developing user interfaces, I've come across (and been rather pleased with) the paradigms of functional and reactive programming (and their esoteric offspring, functional reactive programming).

*I suspect that these two paradigms enable and explain much of benefit that non-programmers get from using Excel.*


#### Portrait of an Excel User
My observation of the typical enterprise Excel user is as follows:

* Cmpetent as computers users (but won't **ever** build their own Linux kernel)
* Very comfortable with Algebra and possibly Calculus


#### Why Non-programmers Love Excel
*...or at least succeed admirably at using it effectively*

* Terrible variable names: but as has been said "There are only two hard problems in Computer Science: cache invalidation and naming things (and off-by-one errors)." The Excel user need never name a variable.
* No appreciable abstraction mechanisms: the ability to think in terms of abstraction and indirection is a skill even many programmers struggle with (a.k.a. "pointers are hard").
* Sheets/Workbooks are the only mechanism of organization: little-to-no paradox of choice.
* Any change, anywhere, any time and the **entire system reacts immediately**. 
* Mutation and managing state are not the user's job; a cell is either a fixed value or it is a **function** of other cells.
* Debugging is so trivial it doesn't even need a name; just look at the data in a cell.

*and for comparison...*


#### Why Many Programmers Dis-like Excel
*...but still use it anyway*

* Terrible variable names: $A$1 may be a valid name in Java (really, try it!) but it is definitely not a *good* name.
* Lilliputian abstraction mechanisms: Excel doesn't even have custom functions (this isn't quite true when VBScript is considered - but how many "self respecting" programmers are going to get near that?)
* Sheets/Workbooks are the only mechanism of organization: no packages, no jars, no assemblies ... no dependency management, no versioning; no flexibility!


## In Short

#### No Paradox of Choice
*Excel removes a lot of decision points that programmers need but which leave non-programmers in a paradox of choice.*

#### Reactive
*Excel responds immediately to the user's input.*

This behavior is likely implemented using some flavor of an event-driven architectures. However another abstraction, Reactive Programming, is layered on top.  This paradigm handles changes in state and provides an intuitive and interactive experience to the user.  The data itself is separated from the functions on that data and everything responds to change immediately.

#### Functional (Not Imperative)
*Excel is just data and a bunch of functions on that data.*

And, those functions are hardly more difficult than Algebra and basic boolean logic.  No side effects; just input(s) and output piped into the cell containing the function.  No uncontrolled mutation or state to be explicitly managed; only cells are mutable (this reminds me of Clojure's refs and STM).  No telling the computer *how*, just *what*.


## Putting It All Together

Excel is certainly no panacea.  Neither are the functional nor the reactive programming paradigms.  Each is a tool.  What I find most interesting is that this pair of paradims seems to be key in enabling large swaths of non-programmers to effectively write custom software that meets their needs.

*If the functional and reactive programming paradims are so approachable to non-programmers, they might just be world-class tools for the professional programmer's toolbox.*