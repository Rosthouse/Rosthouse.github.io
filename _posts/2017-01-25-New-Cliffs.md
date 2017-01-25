---
layout: post
title:  "NEW CLIFFS!"
date:   2017-01-25 16:12:00 +0100
categories: unity bouncer gamedev
tags: unity gamedev bouncer 3d 2.5d
---
As I said last week, today I finally got to have a full day of gamedev for me. And I actually managed to work quite a bit.
Mainly I worked on two things: Spawning and Theming

## SPAWNING LESS ANIMALS!
I decided that I need more control over how animals are spawned. So started messing with the spawning code. Pretty successfull I'd think, just a few keystrokes later I got this:
![OVERFLOW]({{ site.url}}/assets/img/NEW_CLIFFS/OVERFLOW.png)

Totaly intentional, obviously. 
The problem with my previous system, was the time-based approach I took. Meaning, I would create a new animal after a fixed amount of time. This amount of time would be decreased over time as well. Also, I randomized between a maximum and minimum amount of time needed to spawn a new animal.
Also, I needed to make sure to not overwhelm  the player, meaning only a fixed amount of animals can be on screen (or in the air, to be more precise).
That's already 4 parameters needed to spawn an animal:
+ A maximum spawn time
+ A minimum spawn time
+ A timer to decrease the spawn time
+ A maximum amount of animals in the air.

This is the basic algorithm that worked out when to spawn a new entity:
1. (Spawn an animal, let's take that as a starting point)
2. Sleep for between min and max spawn time
3. Check if the spawn timers have to be shortened (spawning more animals quicker)
4. Check if less than the maximum allowed animals are in the air
5. If so, spawn an animal,
6. Else, go to step 2a

After looking at that system more closely, I wanted to simplyfiy it. What I really need is controll over how many animals the player is currently handling. A time based approach isn't really needed.
So the new system does something else:
+ It checks how many animals are currently in the air.
+ If that is lower than the current max animals, spawn a new one.
+ If the score has passed a threshold, increase the max allowed animals.
+ Sleep for 2 seconds and do it again..

I have the feeling that the new system is easier to manage and predict, meaning tweeking gameplay should be easier.

Anyway, with this new system, the player only ever has a finite amount of animals to handle.

## CLIFFS!
While discussing the game with my GF, she mentioned that the game doesn't really have a story. It has knights, a tower, a stable and funny looking animal heads. But that's just some random theme applied, it doens't have any sense behind it.
After giving it some more thought, I decided to switch the theme of the game. You're not sorting animals anymore, but rather saving lemmings from their certain doom.

The lemmings throw themselves off a cliff, and it's up to you to bounce them into a safe place. I think with this, the theme comes better together. While lemmings throwing themselves off a cliff is a myth, it's still something that people seem to know.

This also meant that a lot of things had to go. Mainly, the knights, the funny looking animals, the medieval tower. Just about anything. This is what I came up with:

<img src="{{site.url}}/assets/img/NEW_CLIFFS/OLD_TOWERS_INGAME.png" width="50%"><img src="{{site.url}}/assets/img/NEW_CLIFFS/NEW_TOWERS_INGAME.png" width="50%">
Left is old, right new.

Now the fancy stuff is actually in the editor. See, right now I don't have the skill to draw a proper cliffside. But I do have some 3D Models (courtsy of [Kenney](http://kenney.nl/assets)) which I was able to stick together!

![OLD TOWER EDITOR]({{site.url}}/assets/img/NEW_CLIFFS/OLD_TOWERS_EDITOR.png) ![NEW TOWER EDITOR]({{site.url}}/assets/img/NEW_CLIFFS/NEW_TOWERS_EDITOR.png)
Upper is old, bottom is new.

It's surprisingly easy to create assets this way. Also doesn't seem to be too taxing on a mobile.

## STAY TUNED!
Next week I will rework the background of the game. I want it to be a raging river, threatening the poor lemmings.

Until then, stay tuned.