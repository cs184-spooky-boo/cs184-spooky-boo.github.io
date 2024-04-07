---
layout: page
title: proposal
permalink: /
---

# Spooky Boo

Group Members: Anya Agarwal, Christy Quang, Janani Sriram, Tia Jain

![pumpkin](/assets/img/proposal/pumpkin.jpeg){:style="display:block; margin-left: auto; margin-right: auto; width:50%;"}

### Summary

For our project, we will be making a spooky scene with multiple objects, both moving and stationary. We will use various textures and shaders to model these items’ material — for example, a wood texture for a table, or a thin fabric (i.e satin) texture for a ghost. We also intend to add environmental factors such as wind to make the ghost fabric move and flickering illumination within the pumpkin.

### Problem Description

In previous homework assignments, we haven’t worked with both stationary and moving objects simultaneously. We want to combine what we learned in Homeworks 3 and 4 to generate a scene that supports static and dynamic objects, since that mimics scenes in the real world best.

**Challenges:** 
1. Staged wind movement represent real world movement (ex: the ghost's fabric moves with the correct speed)
2. Learning how to use Blender or Autodesk Maya to 3D model the different objects in the scene (ex: pumpkin, different cloth used for the ghost's fabric)
3. Handling interactions and collisions with other rigid objects
4. Integrating both static and dynamic components in one scene

**Ideas:** For rendering, we might extend our ray tracer from Project 3 or look into more optimized renderers. For simulation, we are looking into [material point methods (MPMs)](https://en.wikipedia.org/wiki/Material_point_method) and how to simulate multi-phase materials. Another approach might be to extend our mass-spring mesh models, though this wouldn't be able to simulate jello breaking. 

### Goals and Deliverables

Main Deliverable: 
We plan to create the shaders and textures needed for our scene. This will include wood, grass, fabric for the ghost, pumpkin skin, metal for some chairs, and more. The shaders, specifically the fabric and grass, will be able to still look realistic while moving.

Our Hope:
Our aspirational plan is to have the environment make more of an impact on our scene. We could potentially have varying gusts of wind blowing in the scene or allow the user to interact with our scene by being able to change the wind gust speed. We could also make multiple textures interact — for example, the ghost brushing against the pumpkin skin by allowing the user to move the ghost or pumpkin.

To showcase our final result, we will record a video of our scene with all of the different functionalities displayed. This will include all of the moving parts, and how the shaders interact with light when the model is moving. The stationary objects will also be hit with the light source, showing the details of the texture that we created. We can also potentially zoom in the camera on certain parts of the scene.

Quantifiable metrics are difficult to define for this project, but we plan to qualitatively view the elements in the scene and compare them to how they would appear in real life. For example, we will examine how realistic the texture of the pumpkin’s skin is. We can also check how smoothly the ghost’s cloth flutters in response to wind, and how smooth the metal of the chairs is. 

With the different types of illumination/lighting, we can measure the timing differences in how the scene is generated. Since the scene has a multitude of objects and factors, this leaves room for the possibility of determining what tradeoffs are more important (i.e sacrificing visual detail for faster generation time).

Questions We Plan to Answer With Our Analysis:
* In what ways can environmental factors like wind and light affect a scene?
* How can different textures interact with each other in one scene? 
    * Within one object, like a pumpkin, how would multiple textures interact? 
    * What do points of contact between textures look like (ex: the contact points between the wood of a stem and the smoothness of the skin)?
* In what ways do static and dynamic objects interact with each other in a scene? How do elements like lighting and shadows affect these interactions?

### Schedule

Week 1 (4/2/2024 - 4/7/2024):
* Model: Various objects in scene (pumpkin, table, chair, candle, etc)
* Textures: Render static objects
  * Pumpkin, wooden table, anything that is intended to be stationary to render individually, then all together in one scene

Week 2 (4/8/2024 - 4/14/2024):
* Shaders: Render dynamic objects
    * Add realistic simulation to the moving object alone (ex: candle flickering)
* Milestone deliverables

Week 3 (4/15/2024 - 4/21/2024):
* Add physics simulation to the moving object (ex: gravity)
* Shaders
    * Shaders may be complicated enough to require 2 weeks, so we are keeping this as a buffer week to finish that up from the previous week.
    * We also intend to spend a lot of this week studying for the midterm on 4/22 this week so may not have as much time to get things done.

Week 4 (4/22/2024 - 4/28/2024):
* Make the scene cohesive and realistic
    * Have static and dynamic objects interact (ex: flickering light should cause shadows and lighting changes on the pumpkin skin)
* Stretch goals

### Resources

- [Grass texture](https://developer.nvidia.com/gpugems/gpugems/part-i-natural-effects/chapter-7-rendering-countless-blades-waving-grass )
- ShaderToy
    - [Cloth/fabric](https://www.shadertoy.com/view/MldXWX)
    - [Wind](https://www.shadertoy.com/view/MdGBWG)
    - [Flickering candlelight](https://www.shadertoy.com/view/ltXyDM)
- Wood Texture in Blender
    - [Make This Easy Procedural Wood Material In Blender (With Just 10 Nodes)](https://medium.com/@samuelsullins/make-this-easy-procedural-wood-material-in-blender-with-just-10-nodes-c94a3f8b54ad)
    - [Blender 3.0 Natural Wood Material In Under 2 Mins!](https://www.youtube.com/watch?v=Egd_BNAT3l8)

### Platforms

* GLSL (Homework 4 Part 5: Shaders)