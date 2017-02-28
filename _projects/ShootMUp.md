---
layout: project
title: ShootMUp
permalink: /projects/shootmup
description: Writing my own game engine using LibGdx!
image: /assets/img/projects/shootmup/shootmup_header.png
---
Before diving into [Unity](https://unity3d.com/), I started out with [GameMaker](http://www.yoyogames.com/gamemaker). It was a fun software, but as I said in [another]() post, I'm not currently using it.
But here is an (at least playable) prototype created with it.

## SHOOTMUP
Alright, so here's the gameplay:
<iframe width="480" height="800" src="https://www.youtube.com/embed/FKo8YeDYGjQ" frameborder="0" allowfullscreen></iframe>

As you can see, it's a pretty standard shooter. I didn't get very far with developing it, but the core gameplay is there.

The idea was to create a vertical scrooling shooter that you could play with only one finger. So all actions had to be somehow mapped to your ship. Here are a few examples of what that meant:
- Shooting
Your ship is constantly shooting. In order to increase your firerate, you have to move your ship in the upper part of the screen. This also meant that your cannon starts overheating. So you constantly had to manage your firerate versus your cannons heath meter.
- Bombs
Bombs (if you picked one up) are released when you lift your finger from your screen. This meant that as soon as you picked one up, the bomb is live! This is really fun, because most time when you need a bomb, you're in deep trouble. So you have to be brave enough and lift your finger for just a moment and for a split second leave yourself open to getting hit (since you're not moving).