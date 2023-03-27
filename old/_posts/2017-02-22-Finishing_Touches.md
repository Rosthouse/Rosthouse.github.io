---
layout: post
title:  "FINISH IT!"
date:   2017-02-15 20:16:00 +0100
categories: unity bouncer gamedev 'save the lemmings'
tags: unity gamedev bouncer motivation postmortem save the lemmings
author: Rosthouse
---
IT IS DONE! SAVE THE LEMMINGS IS DONE!

## DONE!
I added the finishing touches to "Save the Lemmings!" (formerly known as boucer). I completly redid the captain, his boat and his animations. They are a lot smoother now and his jacket looks a lot better.
![Better animations]({{site.url}}/assets/img/posts/finishing/new_animation.gif)

Also, the 'Game Over' Screen now features the buoys as well.
![New Game over screen]({{site.url}}/assets/img/posts/finishing/new_game_over.gif)

After all that, I can call the game finished. I even made a trailer for it! Bask in all its glory.

<video width="1280" height="720" controls>
     <source src="{{site.url}}/assets/vid/posts/finishing/bouncer_trailer.mp4" type="video/mp4">
</video>

## POSTMORTEM!
As is common with indie (or private) games today, I want to do a postmortem. Here I reflect on the development, what went wrong, what went right and what I will take with me.

### WHAT WENT RIGHT!
#### WORKING A DAY A WEEK!
At the start of this year, I managed to reduce my workload (to 80%). Meaning I have a whole day during the week where that I'm able to completly dedicate to game development. 
This decision I made for two reasons:
1) I was getting frustrated with the small amount of progress I was making during the week. It always took me way to long to get into the development mindset. Doing that each day and then only getting ~2 hours of actuall development time was just too little for me.
2) Giving my brain a break. At my day job, I mostly create java interfaces, which is about as fun as it sounds. My mind always races to the creative stuff I could actually work on. Having this day where my brain can go nuts helps my actual day job.

So far I do not regret this decision. Of course my pay has been reduced, but right now I'm doing well enough for myself. I don't have any major spendings planned, so it should work out.

#### DITCHING GAMEMAKER FOR UNITY!
[Gamemaker](http://www.yoyogames.com/gamemaker) is an amazing piece of software. In recent years, it produces many-a-great game (Hotline Miami, Hyperlight Drifter to name a few) that really showed of its potential.
However it was not for me. I always had the feeling that I was fighting the tool instead of working with it. The language (GML) was especially taxing; although easy enough to learn, the limitations start to come in quite quickly.

Going over to Unity, the learning curve was way steeper. But by creating bouncer, I learned the tools and the insides of this engine. Although I didn't venture very deep (no networking, 3D, leveldesign, etc), I feel that I know enough to take on a bigger project.

#### CREATING SOMETHING FOR MY SCOPE!
'Save the Lemmings!' is a very easy game. It has a limited set of actions and only one level, so to speak off. This helped me to really create one game from start to finish.
It's not a game that I would play for hours (although the GF seems to like it :)). I specifically decided to work on a game that I would have no problem with finishing eventually. Now it's february and I can say that already.

### WHAT WENT WRONG!
#### TOOL CREEP!
Something I didn't expected was the amount of new tools I had to learn. In no particular order:
- Inkscape
- Anima2D
- 

#### REDOING ALL THE ART!
Mid-development I decided to change the theme for the game. While in the end I think it payed out, it was a chore to work through. I had to redo a lot of my prefabs, since I didn't build them to be easily changeable.
I had to reprogramm some of my code to work with the new assets. All in all, it was a mess.
If I had built the game from the start with prototyping artifacts (You know, rectangles, circles and the like) I would have known from the start that my art will be replaced and would have had to build it with that in mind. This is something that I will take with me.

#### ASSET MANAGEMENT!
A lot of my assets that are in the project right now are not needed. Either they were from something I tested or were replaced later on. But by far worse is my project structure.

![LOOK AT THIS MESS!]({{site.url}}/assets/img/posts/finishing/messy_project.png)

There are
- unused plugins
- unsused assets
- NO structure (some scripts for example are just floating around somewhere)

This is something I really need to get right the next time, especially if I want to work with other people on a project. Maven is great in that regard, it forces you to use a certain structure in your projects. I wonder if one could do something similar in Unity.

## CLOSING THOUGHTS!
'Save the Lemmings!' sure has parts that I would like to improve. The controlls could use a bit of work, I could add a highscore list, powerups and many more things. But I'm also happy with what it is an how it turned out. It all started with a small bug in a space invaders clone :)
I will publish this on the play store and send it to a few friends. Afterwards I will post it in reddit (maybe also on imgur).

## UP NEXT!
Next week I will start with a new project. Don't know what it's going to be, but I want to have something playable in at least 2 weeks time.

STAY TUNED!