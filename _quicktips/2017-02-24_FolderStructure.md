---
layout: quicktip
permalink: /quicktips/folderstructure
title: Folder Structure
description: How to organize your assets folder
---
Unity lets you run wild with how you organize your assets folder. No matter where a script is, a texture resides or a sound clip has taken residecy, Unity will find it and link it correctly (thanks to the meta file system, I believe).
However, that just calls for trouble. I thought about it and would like to present my folder structure.

## STRUCTURE!
Lo and behold, this is the structure I work with.
- Assets
    - Audio
        - Ambient
        - Effects
        - Soundtrack
    - Graphics
        - Animations
        - Materials
        - Models
        - Textures
        - Shaders
    - Objects
        - Prefabs
        - ScriptableObjects
        - Scenes
    - Packages
    - Resources
        - Audio
        - Graphics
        - Objects
        - Scripts
    - Scripts
        - Editor
        - Behaviours  
    
### Audio
This folder contains all audio clips. I made a distinction between Ambient, Effects and Soundtrack.
- Ambient<br>
These are soundclips that add ambience to a scene. For example, the rolling of waves on a shore, the constant chatter in a tavern or the crackling of a fireplace.
- Effects
These are soundclips that play when an event occures. A door slams shut, a gun is fired, a character is hit.
- Soundtrack
Pretty self-explanatory, this is the music that plays in your game.

### Graphics
Everything that affects your visuals resides in this folder.

### Objects
All your gameobjects (prefabs and such) reside in this folder.

### Packages
Unity allows you to to import many packages from the asset store or from third-party sources (Kenneys game assets for example). However, if you leave them just as they are, they can quickly clutter your assets directory. So I move them to a common place.
Everytime I import an asset package, I move them to this folder. In there, I wont do anything with them. Meaning, I won't force the structure I use outside of the packages folder inside it. So no moving models to a packages/graphics/models folder.

### Resources
Sometimes you have to be able to load resources (be those prefabs, scenes, )

### Scripts
- 