---
layout: post
title:  "Unity and Unit Testing"
date: 2018-07-15 21:11:00 +0200
categories: programming Unity TDD
tags: programming unity unit testing TDD
author: Rosthouse
---
I'm trying hard to wrap my head around working with unit tests in unity. Unit testing seems to be quite an afterthought for Unity, but I find it important for my work and so I try to use it as often as (reasonably) possible.
In Unity 2018.2.0f2, there seem to be some changes that make working with unit test even harder, so I try to document my stuff here.

# Official Documentation

The official documentation about the [Test Runner](https://docs.unity3d.com/Manual/testing-editortestsrunner.html) is sparse at best. It tells you a few things, but I still had to dig around to find everything I need.

# Assembly Definition Files

First, if you want to do any sort of playmode tests, you need to work with [assembly definition files](https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html). These are actually a pretty neat idea and here have the additional benefit of separating your tests from your code.

So, you create a folder (which I conveniently named 'Tests') and inside that folder you create an assembly definition file. A tab will open in unity, there make sure that beneath 'Unity Reference' the checkbox for 'Test Assemblies' is checked.

![Assembly Definition File]({{ site.url}}/assets/img/NEW_CLIFFS/OVERFLOW.png)

Very observant readers will see, that I already have a reference to another ASDF marked there. Unfortunately, in order to work with ASDF tests (which are required for play tests), we need to create another ASDF for ALL our other scripts. So if you have your scripts all over the place, now may be a good time to put them all in one folder structure. I recommend creating a folder under 'Assets' called 'Scripts', 'Code' or something similar.

As soon as you're done, you can open your solution in VS again.