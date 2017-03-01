---
layout: project
title: Mermelin
permalink: /projects/mermelin
description: Game & Engine written for our Bachelor Thesis!
image: /assets/img/rosthouse.png
---
For my master thesis, we wanted to explore the posibilities of shaders. Specifically a game where the effects of a shader had direct impact on the gameplay.

## THE PLOT!
In a previous project we created a basic engine (which, to the end, ran on both windows and linux). With this framework we started brainstorming ideas.

We came up with a game idea based upon the Kugellabyrinth (if there's an english name, please tell me).
![Kugellabyrinth](https://de.wikipedia.org/wiki/Geschicklichkeitsspiel#/media/File:PuzzleOfDexterity.jpg)

In our game you would influence a sphere to roll around in a labyrinth. You would find a wooden gate, which you can't pass. Next you have to find a fire-plate to roll over, setting your sphere on fire. With this, you would then go back to the door and burn it down. Given that you managed to thread your sphere through a narrow path cornered by water.

Given this basic outline, we planned a game based upon the [classical elements](https://en.wikipedia.org/wiki/Classical_element#Greece) fire, air, water and earth. Each element would give your sphere different properties, and allow you to pass different areas. We were even thinking about combining elements, like fire and water would create steam, allowing you to pass fences.

With this basic idea, we started developing.

## ENGINE!
At first, we wanted to use [Unity](http://unity3d.com/), but our professor wasn't comfortable with using a proprietary tool to create a master thesis. So we wrote our own engine, as previously stated.
We built it upon open-source frameworks.

![Engine overview]({{site.url}}/assets/img/projects/mermelin/engine_overview.png)

So that you don't have to look every single framework up, I listed them up here:
- [Ogre3D](http://ogre3d.org/) for graphics
- [Bullet](http://bulletphysics.org/wordpress/) for physics
- [SFML](https://www.sfml-dev.org/) for audio
- [OIS](https://en.wikipedia.org/wiki/Object_Oriented_Input_System) for input
- [libRocket](https://github.com/libRocket/libRocket) for the built
- Custom solution for game logic

Everything was written in C++, save for the shaders who were created with [GLSL](https://en.wikipedia.org/wiki/OpenGL_Shading_Language).

## GAMEPLAY!
We spent most of our time getting the engine to work properly. We weren't used to developing with C++, taking most of our time figuring out how to work with it. On top of that, we also had to learn new frameworks, like OGRE, which didn't help that much.
But in the end, we produced a playable level.

Here's the menu screen:
![Menu screen]({{site.url}}/assets/img/projects/mermelin/menu_screen.png)

And here are screenshots of the different shaders in action. Try to guess which is which ;)

![Air]({{site.url}}/assets/img/projects/mermelin/air_shader.png)
![Earth]({{site.url}}/assets/img/projects/mermelin/earth_shader.png)
![Water]({{site.url}}/assets/img/projects/mermelin/water_shader.png)
![Fire]({{site.url}}/assets/img/projects/mermelin/fire_shader.png)

## WRAPPING UP!
It was a stressfull project and I'm happy that in the end we got a good grade for it. If you're interested in more details, our thesis is [online](https://github.com/Rosthouse/Mermelin/blob/master/media/documentation/Thesis.pdf). It is in german, so beware.

If you're intereste in the project itself, I invite you to peak around in it over at [github](https://github.com/Rosthouse/Mermelin).