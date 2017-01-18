---
layout: post
title:  "Creating a blog!"
date:   2017-01-18 15:52:00 +0100
categories: jekyll update
---
As I am having a little more off time serving my country (lol), I thought I could use this time best if I rig up my blog. The reasoning was that here I wouldn't have a good enought machine to do serious dev work, neither do I have the peace and quiet that I need to work on crazy stuff. So I got my laptop out and started installing jekyll.
#Why jekyll?
I am a developer. I live in code files, I am the command line. I am not the creative type that has photoshop, dreamweaver and whatnot figured out. I thought going with a framework where everything you can do is spelled out in code rather than in submenues of submenuse would be more suited for me.
Truth be told, I also liked that you can simply create a git repo and push that to github.

Maybe I will one day create a proper website, but for now this must suffice. But...
# NOTHING BLOODY WORKS
Ok, all right. The first few steps were rather easy. Just follow the directions on the [Quickstart Guide](https://jekyllrb.com/docs/quickstart/) and you have your basic blog running. And that did work, no complaints there.
But as soon as I started working with themes, everything came crashing down. I had obscure error messages, had to install another ruby framework (devkit?) and in the end I couldn't even get the github themes running on my local machine.
Frustrated I deleted everything and started anew.
# SOMETHING BLODDY WORKS
After I started again, I took another approach. Do I need a fancy theme, with animations, cool shadows and more plugins than I'll ever know?

Nah, I don't think so.

After verifying that everyhting works again (it did) I looked into the basic theme (called [Minima](https://github.com/jekyll/minima)) and checked how I can customize that. And to my surprise, it's rather easy!
I had to create a new folder called ```_layouts``` and add a few template html files. These I took straight off the Minima github page.
I now have these files in the ```_layouts``` directory:
```
default.html
home.html
page.html
post.html
```
These are used to render my pages.
# MORE BLOODY THINGS WORK
Cool, now I am able to change the structure of my blog. So far so good.

But you can't really put a blog out there if you don't have any colors in it. The basic white looks clean, but staring at it too long will make your eyes bleed (Dark themes, each day, every day). So that means getting into CSS, or [SASS](http://sass-lang.com/), as that is used by jekyll. Another new thing to learn.
And again, this seems to work smoothly. The syntax is a bit weird to begin, if you're used to standard CSS. But I see the strenghts given by SASS, which is awesome.

Quickly I wanted to do something more. Have the navbar beneath my blog title. Right now the title is on the side, like this:
![Menu right now]({{ site.url }}/assets/img/18-01-2017_right_hand_menu.png)

My first hunch was to do this in CSS.

