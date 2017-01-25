---
layout: post
title:  "More blogging!"
date:   2017-01-19 16:52:00 +0100
categories: jekyll update blogging
tags: syntax highlighting jekyll sorting order favicon logo css
---
After working a little more with [jekyll](https://jekyllrb.com/), I'm really starting to like it. It's quite easy, once you get the hang of it (safe for CSS/SASS, but that's a nightmare everywhere).
So I'm posting a few handy snippets I found.

## WORK FROM THE SOURCE!
My jekyll theme is based upon the [minima theme](https://github.com/jekyll/minima). Basically anything I did was by looking at the source and modifying what I had to.
In this post, whenever I talk about add this or add that file, I just downloaded it from the git repo and added it.

## SYNTAX HIGHLIGHTING!
First, to create this post, I actually had to figure out how to display jekyll and html code in this blog. What you need is to use the ```{ % raw % }``` tag to encapsule your liquid code (I deliberatly put a space in between the curly braces and the percentage sign here). Otherwise, the page generator will read your code even if it is in an highlight tag. And we don't want that.

## ORDER YOUR PAGES!
One of the first things I wanted to do, after creating my projects collection, I wanted to be able to sort my pages. I was really happy to see that this can be quite easily done!
The code for this I got from [stackoverflow](http://stackoverflow.com/a/33983971)
In the folder ```/_includes```, add the file ```header.html```. There, find the div 'trigger'. Change it to this:
```html{% raw %}
    <div class="trigger">
        <a class="page-link"  href="{% raw %}{{ "/" | relative_url}}{% endraw %}">Home</a>
        {% raw %}{% assign sorted_pages = site.pages | sort:"order" %}{% endraw %}
        {% raw %}{% for my_page in sorted_pages %}{% endraw %}
            {% raw %}{% if my_page.title %}{% endraw %}
            <a class="page-link" href="{% raw %}{{ my_page.url | relative_url }}{% endraw %}">{% raw %}{{ my_page.title | escape }}{% endraw %}</a>
            {% raw %}{% endif %}{% endraw %}
       {% raw %}{% endfor %}{% endraw %}
    </div>
```
Let's go through that. Instead of simply looping through the pages, what you do instead is sort them by a property ```order```. This property can simply be defined in the frontmater header of a page, like this:
```
---
layout: page
title: Links
permalink: /links/
order: 3
---
```
Next, I just loop over the list ```sorted_pages```, giving me exactly the order I defined previously.
*Sidenote* I also added a Home Button to my nav page. It just seemed to be missing for me.

## ADD A FAVICON!
First, you obviously need a favicon. Create one and put it into the root directory of your page.
For me, it didn't show up at first. So again, I had to modify the source. In the folder ```/_includes```, add the file ```head.html```. There, we add a ```link``` tag to the head.
```html
<head>
    ...
    <link rel="shortcut icon" type="image/x-icon" href="{%raw%}{{ "favicon.ico" | relative_url }}?{%endraw%}">
    ...
</head>
```
This should work without any more modifications. Save and test.

## ADD A LOGO!
Ok, this here is more a reminder to myself, but I promise I can show you a pretty neat CSS trick in the end.
I made myself a little logo (hurray) and wanted to use it for more than just a favicon. My idea was to include it on the top right side of the page, same hight as the blog title. Seemed easy enough, I thought.

I changed this line in the ```header.html``` file
```html
<a class="site-title" href="{%raw%}{{ "/" | relative_url}}{%endraw%}">{%raw%}{{ site.title | escape }}{%endraw%}</a>
```
to this
```html
 <div class="site-title">
    <a class="site-left" href="{{ "/" | relative_url}}">{{ site.title | escape }}</a>
    <img class="site-right" src="{{ "/assets/img/logo.png" | relative_url }}" alt="logo" >
</div>
```
After that my page looked like this:
![Logo Test 1]({{ site.url }}/assets/img/19-01-2017_header_logo_1.png)
Allright, no worries. Just float these and it will work out perfectly.
```sscss
.site-title{
    float: none;
    .site-left  { float: left; }
    .site-right { float: right; }
}
```
This should do the trick, next I...

![Logo Test 2]({{ site.url }}/assets/img/19-01-2017_header_logo_2.png)
Oh... Well that isn't what I wanted.

After looking around a little, I got the problem. I have to tell the browser to stop floating elements as soon as I don't want them to float anymore. That means checking what the next HTML element is in my tree and add this CSS tag to it: ```clear: both;```
What I don't like about this solution is that the NEXT element basically has to clean up the mess of the previous element. 
After looking around, I foudn this:
```scss
.site-title{
    float: none;
    .site-left  { float: left; }
    .site-right { float: right; }
    &:after{
        content: '';
        display: block;
        clear: both;
    }
}

```
Whith the after element, I create an invisible HTML element, that clears up the floating. It's a bit of a hac, but works pretty good:
![Logo Test 3]({{ site.url }}/assets/img/19-01-2017_header_logo_3.png)

## MORE TRICKS TO FOLLOW!
I will be posting more such tricks in the future. It's a nice challenge to figure out such things and provides me a break.

## NEXT WEEK!
Next week I will (finally) really start working on games. I intend to work on Bouncer again and change the aestethics of the game to have a "Fjord" theme instead of a medival one.
Hopefully I can post a better project page after that.