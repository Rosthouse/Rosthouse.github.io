---
layout: quicktip
permalink: /quicktips/UnityEventsGizmos
title: Visualize UnityEvent
description: Show your UnityEvent dependencies in the editor.
---
[UnityEvents](https://docs.unity3d.com/Manual/UnityEvents.html) are an awesome tool to work with, since they allow you to decouple your GameObjects quite neatly. However, if you use them a lot, it's easy to have a mess of different events all over the place. With this quick tip, you can visualize all connections directly in the editor!

## CODE!
In a [MonoBehaviour]() that exposes a UnityEvent, add this function:
{% highlight csharp %}
function DrawGizmosSelected()
{
    //Draw code
}
{% endhighlight %}