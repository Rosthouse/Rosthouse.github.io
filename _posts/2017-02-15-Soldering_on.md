---
layout: post
title:  "SOLDERING ON!"
date:   2017-02-15 20:16:00 +0100
categories: unity bouncer gamedev
tags: unity gamedev bouncer motivation
author: Rosthouse
---
I did pretty good today. Yeah, I think I did. Not only did I continue working on the project I want to finish, I actuall was able to improve quite a few things.
And Unity starts feeling... familiar?

## LOGO!
I created a new Logo!

![New Logo]({{site.url}}/assets/img/posts/soldering_on/new_logo.gif)

Aliasing is way better, the drop-shadow actually looks correct and I just love the skewing. I used Inkscape to create it.

Inkscape itself starts to be useful for me. So far I've only scrapped the very top of the many useful features it provides. But as new feature requests (by myself, for myself) start comming in, I have to figure this tool out.
Todays new finding: [Patheffects](http://tavmjong.free.fr/INKSCAPE/MANUAL/html/Paths-LivePathEffects.html). I used these to create the bent path that the text follows:

![Bendy]({{site.url}}/assets/img/posts/soldering_on/bendy_path_in_inkscape.png)

Pretty neat!

## NEW MAIN MENU!
The main menu has changed completly as well. It now better mirrors the main game, which I think is a good thing:

{% video {{site.url}}/assets/vid/posts/soldering_on/new_main_menu.mp4 480 800 %}

The buoys (which sounds funny in english) are actually 3D models, similar to the cliffs. What's neat though, is that although they all use the exact same animation, I managed to randomize them a little. First, the speed of each buoy is randomized in a certain range (configurable, see below). Second, each animation starts at a randomized offset. That means that each buoy has a different rythm and start point.
For each of these parameters, I created animation parameters (floats) and attached them to the animation state:


![animation state]({{site.url}}/assets/img/posts/soldering_on/animation_variables.png)

Afterwards, I can randomize these in a MonoBehaviour.

## CUSTOM EDITORS!
I created my first Custom Editor today! Yay me.
Was a pretty simple editor really. As said in the previous topic, I control the animation speed over a variable. This variable has to be somewhere between 0 and 1, althoug I don't want it to be 0 (no animation in that case).
So I created a small editor:

{% highlight csharp %}
[CanEditMultipleObjects()]
[CustomEditor(typeof(StartAnimationWithOffset))]
public class StartWithRandomOffsetEditor : Editor
{
    public override void OnInspectorGUI()
    {
        StartAnimationWithOffset myTarget = (StartAnimationWithOffset)target;
        EditorGUILayout.LabelField("Min Val:", myTarget.minSpeedModifier.ToString());
        EditorGUILayout.LabelField("Max Val:", myTarget.maxSpeedModifier.ToString());
        EditorGUILayout.MinMaxSlider(
            new GUIContent("Random range:"),
            ref myTarget.minSpeedModifier, ref myTarget.maxSpeedModifier,
            0.0f, 1.0f);
        EditorUtility.SetDirty(target);
    }
}
{% endhighlight %}

Instead of showing 2 floats in the editor, I get a slider with which I can set a range:

![minmax editor]({{site.url}}/assets/img/posts/soldering_on/custom_editor_minmaxslider.png)

I can already see how useful stuff like that will be in the future.

## SCENE TRANSITION!
So far, when I changed from the menu to the game, what happened wasn't... pretty. I would just load the next scene and be done with it. But if I want to publish this game, I have to do something a bit smoother. So I devised a way to change my scenes.
I took inspiration from theatre. Whenever they change a scene, the curtain would drop, some elves hop onto the stage, swap the scenery, scurry under the stage again and the curtain was lifted. I wanted to have a similar effect.

At the bottom, I have my waves. I thought I could use them as an inverted curtain, going up when I change my scene and comming down again when everything is loaded. Currently looks like this:
{% video {{site.url}}/assets/vid/posts/soldering_on/scene_change.mp4 480 800 %}

## VIDEOS!
After trying many tools (still like ScreenToGif), I decided on Snagit. I know it from work and it's just the best screen recording tool I've found so far. Also, it produced the smallest possible videos I could so far.
Although I'm thinking about uploading my videos and images to other websites like [youtube](https://www.youtube.com) and [imgur](https://www.imgur.com), since these take up the majority of space of my website. I'll have to think about it some more.

## STAY TUNED!
I'm so close to finish this thing. I know it. Hopefully I can release a public beta next week.

Until then, keep developing!