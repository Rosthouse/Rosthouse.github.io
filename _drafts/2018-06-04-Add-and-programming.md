---
layout: post
title:  "ADD and Unit Testing"
date: 2018-06-04 21:11:00 +0200
categories: programming ADHD TDD
tags: programming adhd unit testing TDD
author: Rosthouse
---
# A normal day at the office

So let me tell you a story. Today I had to implement a new feature, where I had to fill up empty values in an SQL table with default values. Easy right? Well we already had a lot of code for reading values out of said table and saving it back. I started of quite good. I made a class, wrote tests for the merging, tests for iterating over the merged values and saving them back (Mind you, DB connection was completly mocked).
I thought, well I have enough functionality, and the rest is just data crunching. No big deal. So I threw together the rest of the functionality, without bothering to write tests, and just ran the damn thing.

Of course it instantly blew up in my face. Goddamn it.

After going back, adding in adidtional tests, I quickly found that in the specific method I needed to read values from the DB, I had a mistake. That functionality wasn't tested, so it never failed during testing. After adding tests and recompiling it worked perfectly. Great, only an hour lost, and all because I didn't bother checking everything I used.

Why did I do this? Well being honest, it was getting late and I felt that I already took longer on this feature than I should have. So I tried to cut corners and leave the tests to the side. Also, I was getting bored with the command and I wanted to finish it before I completly lost interest. Well, that didn't work.

What was my mistake? I threw my good standards into the wind and immediatly paid the price. I tried to protect my brain from, but it thanked me with a mess.

After ranting about myself, I want to write this blog post to reafirm my belief, that TDD is a MUST for programmers with ADD

## Why we do it

ADD and programming is a weird combination. It requires concentration, attention span and precision in everything. Yet it seems that many people diagnosed with ADD love programming, or working in IT in general.

Why do we crave to work on those machines? Let's remind us of some properties that the ADD brain puts upon us:

We crave...

1. ... all things new.
2. ... instant satisfaction.

Let's tackle the first point. Everyday we open our web browsers, there is something new. A new technnique, a new programming language, framework, algorithm, tool, you name it. There is enough content EVERY day to fill up a lifetime of curiousity (though for some people, that's still not enough ;) ). This point should be fairly clear.

The second point is clear for everyone who ever opened a terminal. You type something simple in there and instantly get an answer. The more often you do this, the more sophisticated the questions can get. It allows us to instantly see what we are doing. This is imensly powerful.

## Instantly bored

Yet software development is not instantaneous. Programming a piece of software can take weeks, months, years even. Sometimes when you write a line, you won't see the result of it for quite some time, just because the surrounding framework is not yet existing. This leads you to forget things. Sometimes I feel like an archeologist, wading through unknown dungeons, just to stumple upon an artifact. Proudly I take it out of the dungeon, only to later find out I had already been there before and found my purse there that I've lost the last  time I visited.

This leads to problems. Seeing the mountain of work that is necessary to run a piece of software can instantly shut off your brain. There are more interesting things to see on reddit anyway, so why bother? When you do write some code, it will most likely not fit together with what you did already, be it because you forgot how it actually worked or that you intendet it for something else.
Code Quality suffers, bugs appear and your motivation tanks.

Bummer

## Unit test

To prevent these problems, I found that TDD is a prefect companion for the ADD programmer. Mind you, I won't go into the discussion if it is sensible to write tests for your software. The way I use TDD is mostly for helping ME to write quality software.

Should you never have heard of TDD, it goes something like this:

1. You think of some code you need.
2. You write a test for it.
3. You run the test you just wrote and let it fail.
4. You implement the code that you beliefe will let the test pass.
5. You run it again. If the test suceeds, you're done, otherwise you return to point 4.

Now, why does this fairly simple pattern work for me. Let's look at the things that the ADD brain craves for again:

1. We crave all things new
2. We crave for instant satisfaction

We tackle the first point first again. Every time you write a unit test, you are creating something new. It enables you to push forward, to see your code grow. 

The second point should be obvious. Instead of waiting for hours to see if what we did is correct, we get a result instantly and see if the code we wrote behaves like we expect it to. Its this tight loop of writing test and running it that gives us an instant satisfaction. For me, it's greatly motivating to see my tests turn green in the knowledge that I created something that works.

## Long term benefits

So as we saw (or rather, as I claim), unit tests allow us to push forward with our code and gives us an instant satisfaction. However, I value the long term benefits even stronger. Another problem that often behooves me is coming back to old code and changing it. Now, some code is used all over the place and is expected to work in a certain way. If I change it, I want to be sure that it won't break any other functionality I have in my code.

If I don't have unit tests, I would need to check every single call made to that code, check the inputs and recheck if my code works under all conditions that I previously envisioned.

But If I have unit tests, this becomes as simple as rerunning all the tests I wrote previously. If some (or god forbid, all) turn red I know that I fucked something up. I know where to check and I reafirm my knowledge into the code I just changed.

## No silver bullet

Be aware that writing unit tests does not mean that your code is bug free. And trust me, you will still find bugs even when working strictly with TDD. But it does enable you to find bugs faster and fix them without breaking anything else (or at least, the probability is lower).

Remind yourself. You don't write tests because you suck at programming. Don't fall into the trap of being a wiz kid and claiming that you can write code that will never fail. Nobody can. Take that from a former wiz kid.

## Tips

Here are some random tips that I had to discover:

1. Don't write every test imaginable. Write just enough test for you to see that your code works.
2. If you're wondering how a piece of code works, write a test for it.
3. If you think "I should implement that later", write a failing test for it. That way you won't forget it.
    a. Most tools should allow you to mark tests that should be skipped. Use it, but also remind yourself to eventually go back and implement those skipped tests.
4. Do rewrite your tests. Tests should not be set in stone, they should be living and changing with the rest of your code.
5. Run them often, fix them as soon as they fail.