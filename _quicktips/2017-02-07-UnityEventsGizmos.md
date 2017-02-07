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
UnityEvent activate;

private void OnDrawGizmosSelected()
{
    for (int i = 0; i < activate.GetPersistentEventCount(); i++)
    {
        Object listener = activate.GetPersistentTarget(i);
        MonoBehaviour target = listener as MonoBehaviour;
        if (target != null)
        {
            Gizmos.color = Color.blue;
            Gizmos.DrawLine(this.transform.position, target.transform.position);
        }
    }
}
{% endhighlight %}
What it does should be pretty self-explanatory. So I will explain it anyway.
It reads the amount of listeners of the event, then draws a line for each of them, by converting a target to a MonoBehaviour and then reading its tranform.
You could add some bells and whistles, by including more sophisticated gizmos (like drawing a circle at the start and a triangle at the end, creating an arrow), but it works for me that way.
