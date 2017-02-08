---
layout: quicktip
permalink: /quicktips/UnityEventsGizmos
title: Tiling not seamless
description: Show your UnityEvent dependencies in the editor.
---
In Unity 5.6, sprite tiling is revamped. But at first I had troubles getting the seams between the sprites correctly.


## SETTINGS!
After fidgeting around in the settings a little, I found another developer who had the [same problem as me](http://answers.unity3d.com/questions/600341/seams-in-2d-pixel-art.html). While his final answer didn't help me, it set me on the right path.
The problem was that I had [Bilinear Filtering](https://docs.unity3d.com/ScriptReference/FilterMode.html) enabled for my texture. That meant that the edges were blurred, resulting in a seam. When I changed the texture setting to [Point filtering](https://docs.unity3d.com/ScriptReference/FilterMode.Point.html), the seams dissapeared.

![Filter settings]({{site.url}}/assets/img/quicktips/seamless_tiles/set_filter_mode.gif)