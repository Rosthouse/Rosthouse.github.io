---
layout: project
title: RostyEngine
permalink: /projects/rostyengine
description: Writing my own game engine using LibGdx!
image: /assets/img/projects/rostyengine/header_image.png
---
After my bachelor-thesis I couldn't let go of the overall game idea. I also got a new job and was switching from mostly C# development to java development. So it was the perfect time to start a new project, by porting an old game to a new language.

## ROSTYENGINE!
I had a few points I wanted to have in my next game:
- Using an opensource engine (So that my [XNA problem]({{site.url}}/projects/multipac) wouldn't repeat itels).
- Using tools I'm also using at work, meaning
    - Java
    - Maven
    - Netbeans

After doing some research, I decided upon [LibGDX](http://libgdx.badlogicgames.com/) an open source game framework. Mind you, it isn't a game engine, like [Unity]() and [GameMaker]() are, but rather a set of libraries that you have to cobble together by yourself. That said, it makes it fairly easy by being well documented and generating everything you need even for multi-platform development. All in all, I was quite happy with LibGDX. But I had to create my own engine.

### SUPPORTED FEATURES!
Looking back at it, I'm surprised what was in there. I decided early on to use an [ECS](https://github.com/libgdx/ashley) system, so that everything (in-game) would be easily extendable. And I mostly succeeded. I even have support for custom scripts. I guess another day of development would be needed to be able to load external scripts, be that groovy or javascript.

It also included:
- Shader support
- Physics support
- [Tiled](http://www.mapeditor.org/) map loading
- Multiplatform input (worked on both windows and android, with completly different control styles).

If so many things worked, why did I stop?

## STOP WHILE YOU CAN!
Although I'm rather proud of creating a somewhat working engine, the overhead of writing it all by myself was getting way too much, with work also taking a rather large part of my development time away. I guess it's also around the time my GF moved in with me, so that could also be a reason.

But the main part was this: I was not seeing enough progress. Since I had to stop and rework part of the engine everytime I wanted a new feature, it was rather tedious to work on. Note that this is not because the engine was poorly implemented, but rather that I had to learn a lot about the framework on the fly.

But still, it was an important step for me. I could use the knowledge I had built up to this point and actually write useable software. That was nice.

I also learned my most important lesson: GO SMALLER!

## SCREENSHOTS!
After all that talk, let's see what's actually in there:

![First level]({{site.url}}/assets/img/projects/rostyengine/first_level_start.png)
![First level zoomed out]({{site.url}}/assets/img/projects/rostyengine/first_level_zoomed_out.png)
![collision debugging]({{site.url}}/assets/img/projects/rostyengine/debug_collisions.png)
![Secong level]({{site.url}}/assets/img/projects/rostyengine/second_level.png)

## CLOSING THOUGHT!
I learned a lot throught this project. How an engine should be built, how you should organize code and many more things. But as always, I had too big of a scope.

If you want to see this in action, I uploaded the code on [github](https://github.com/Rosthouse/RostyEngine).