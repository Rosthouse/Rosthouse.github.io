---
layout: post
title:  "CAPTAIN MY CAPTAIN!"
date:   2017-02-01 16:12:00 +0100
categories: unity bouncer gamedev
tags: unity gamedev bouncer 3d 2.5d particle
---
Over the last week, I tried to figure out how I'm going to change the layout. There's a lot of stuff that has to change, and even though I thought I could do it quickly, I'm not quite finished.
First and foremost, Robby is gone

## ANIMA2D!
To completly support my new theme, robby had to go. I liked him, but what will he do in water? So I started working on a replacement:

![The captain]({{ site.url}}/assets/img/captain_my_captain/captain.png)

The captain has been tasked with saving the poor lemmings. Not that he's completly fond of the task, but what can he do? Although, it has to be said that he looks better in motion:

![Row captain, row!]({{ site.url }}/assets/img/captain_my_captain/captain_rowing.gif)

Yeah, that's better.
I did this animation with the help of [Anima2d](https://anima2d.com/), which is since last month free on the [asset store](https://www.assetstore.unity3d.com/en/#!/content/79840). Basically, this is something similar to Spriter or Spine, but directly built into Unity itself.
After some troubles starting out (and after binge-watching some tutorials), I figured out my best workflow so far.
1. Setup your sprites the way you like them.
2. Setup the bones.
3. Connect IK Limbs
4. Do poses and save them on the root bone.
<p>_**Warning**_: When doing poses, check that your rotations are in a sensible range. While I was setting up my animations, I suddenly had the paddle of the captain do 360 flips for no reason. Well, no reason, I found that the paddle had a rotation of something like 6353 degrees o0.</p>
5. Create an animation
6. At your keyframes, set your poses in the right order.
7. ???
8. Profit!
It's a bit of a pain, but I think that's more because I'm not yet that good at creating animations and stuff like that. Something I wish I could get better at. Hopefully I'll find an artist that can do that stuff for me in the future.

Anyway, Anima2d in itself is nice. I like that I don't have to learn a completly new tool, but instead can use familiar unity terminology for most things.

## ANIMATIONS!
While working on the captain, I was thinking about how and where he'll use that paddle of his. I decided to create a simple water animation. First I though about writing a shader and making it respond to the captain itself. But I think that's above my skillset right now.
So instead, I used the new tiling features of unity to create a band of waves:

![Water in the editor]({{ site.url }}/assets/img/captain_my_captain/water_editor.PNG)

As you can see, it's nothing more than 3 sprites behind one another.
Next, I animated them, creating a saw-like movement, for each band of wave you can see in the editor. The result is this:

![Waves!]({{ site.url }}/assets/img/captain_my_captain/water_waves.gif)

That was quite easy actually. If you set up your layers correctly, you can even have some sprites go behind one band or the other, so that it appears that your gameobject is between them.

## PARTICLE SYSTEMS!
I wanted to have a bit more movement in the whole game, without compromising gameplay. With a little rain, I thought that I could easily pep the whole thing up.
The particle system of unity is awesome. It only took me five minutes to rig one together that creates a satisfying rain effect:

![Rain!]({{ site.url }}/assets/img/captain_my_captain/rain.gif)

To get this to work, I only had to create a rain material. I adapted one of the existing standard asset particles into one string, and it gave me exaclty the effect I wanted.

| Before      | After           |
| ------------- |:-------------:| 
| ![ParticleFlare!]({{ site.url }}/assets/img/captain_my_captain/ParticleFlare.png)     | ![ParticleRain!]({{ site.url }}/assets/img/captain_my_captain/ParticleRain.png) | 

Simple stuff. But really effective.

I leave you with a first impression of the current gameplay. Enjoy:

![Gameplay!]({{ site.url }}/assets/img/captain_my_captain/gameplay.gif)

## GIFS!
For this blog post, I wanted to add some gifs. Moving images tell more stories than static ones.
After looking on google, I found [ScreenToGif](http://www.screentogif.com/). It's open source and has the easisest interface imaginable. Love it.

## STAY TUNED!
Next week I will continue working on the aesthetics. I want to add more sound and spice up the animations a little. Maybe I'll work during the week on some stuff as well. A powerup wouldn't be a bad thing :)

Till next week!