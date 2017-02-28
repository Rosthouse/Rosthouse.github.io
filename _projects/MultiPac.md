---
layout: project
title: MultiPac
permalink: /projects/multipac
description: Creating a real-time multiplayer pac-man clone!
image: /assets/img/projects/multipac/multipac_header.png
---
Multipac was a game created by 3 students (including myself) to learn about networking.

## GENERAL
The task was to create a small game that is networked. Our professor suggested some games and we ultimatively chose Pacman. Other teams were happy to have it somehow working (mostly by having each player take on step after the other, making a kind of turn-based pacman). I was not satisfied with that. It had to be real-time.

### CLIENT-SIDE PREDICTION
During that time, I was playing a lot of Counter-Strike as well. While I wasn't any good, I was intrigued by the workings of the engine itself. How was it possible that I could play with someone else accross the globe, (almost) in real time?
Luckily, Valve was happy to share some insight in how they did [Client Side Predition](https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking).

After closely studying this paper, I decided to implement a simplified version into our pacman game. And it DID work! It was blazing fast and our game came closest to the real thing.

### CREATING THE GAME
After some discussion with my team mates, we decided to do the game in C#, using XNA Game Studios. This was a good decision. I was using C# at work and had to do the most programming, so I decided for a language that I was most comfortable with. The two other were quick up to speed.
I started working on the engine, creating the graphics and such things, while my team mate started on the server. We used the [Lidgren Library](https://github.com/lidgren/lidgren-network-gen3), which was awesome to use.

I'm still suprised by how fast we got the game to work. And by how much fun I had creating this game. I learned a lot about [ECS](https://en.wikipedia.org/wiki/Entity%E2%80%93component%E2%80%93system), which I would later use in my bachelor thesis.
Here are some screenshots of the actual game:

![Start screen]({{site.url}}/assets/img/projects/multipac/start_screen.png)
![Single Player]({{site.url}}/assets/img/projects/multipac/single_player.png)
![Server screen]({{site.url}}/assets/img/projects/multipac/server_screen.png)
![Multi Player]({{site.url}}/assets/img/projects/multipac/multi_player.png)

## LOST IN TIME
Sadly, I'm not able to build this game anymore. Microsoft abandoned the XNA project (it lives on in [Monogame](http://www.monogame.net/), as far as I know) and it used Visual Studio 2010(!).

If you still find it interesting, please check it out on [github](https://github.com/Rosthouse/Multi-Pac). Although you will have a hard time getting it to work, you can check out the documentation, which should give you an idea how the game itself worked (if you know german, that is).