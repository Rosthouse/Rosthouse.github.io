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
            - NetworkBehaviours
        - ScriptableObjects
    
### Audio
This folder contains all audio clips. I made a distinction between Ambient, Effects and Soundtrack.
- Ambient
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
Sometimes you have to be able to load resources (be those prefabs, scenes, textures) at runtime. Unity supports this for assets that reside in a folder called 'Resources'. To prevent cluttering this folder up, I enforce the same structure inside the Resource folder as I do in the Assets folder.

### Scripts
Each directory in here contains (C#) code. By their naming it should be obvious what goes where, but just to be sure:
- Behaviours
<br>This contains MonoBehaviours, StateMachineBehaviours and all other code files directly inheriting from Unity classes.
- Editor
<br>Classes in here enhance the editor, giving you the ability to create special editors and such.
- CustomObjects
<br>This folder contains all classes that do not directly inherit from a Unity class.

## Advantages
Each Unity developer you ask will probably tell you a different way they organize their folders inside the Assets folder. 

My approach is inspired by [Maven](https://maven.apache.org/) and its [standard directory layout](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html). The key advantage it gives is clarity. It tells you exactly where each file type belongs in your folder structure. Inside them, you are free to choose your own structure (be that scene based, prefab based or anything else). But as long as you keep that general structure you're fine. There's no arguing where you should place the files.

Second key advantage is communication. The structure is laid out so that even for new people it should be obvious how the structure is laid out. Less time is spent explaining new people where they have to look for meshes, textures and scripts.

## Disadvantages
Certainly there are also disadvantages. Mainly that it separates assets that clearly belong to each other. If you have a 3D model that has a single texture and (or) just one material, you still have to put each of these assets in separate folders, althoug it would probably be easier to keep them in one place for simplicity.

Another disadvantage is that you have to be more carefull with creating assets (such as scripts and materials). Management of your files is, while not more difficult, more laborious. You have to check that each script is generated in the right folder or move it after creating it.
Especially in crunch mode this can become tedious, since you just want to get the bloody thing to run instead of fidling around with files and folders.