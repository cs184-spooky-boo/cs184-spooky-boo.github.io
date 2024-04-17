---
layout: page
title: milestone
permalink: /milestone
---

# Milestone
![ghost](/assets/img/milestone/ghost.png){:style="display:block; margin-left: auto; margin-right: auto; width:50%;"}

## Important Links

- [Slides](https://docs.google.com/presentation/d/1-0b0kxSXW2xQeXWxNEVVtFc78-RBjcDXZzXNmsWsY2E/edit?usp=sharing)
- [Recording]()

<br>

## Accomplishments
For our project, we first worked on incorporating wind simulation to our existing cloth simulator from Homework 4 because this would be an essential component towards making our scene more realistic, factoring in the physical dynamic effects on objects.

Additionally, we manipulated the shader (starting point was using the Blinn Phong shader) for the ghost cloth to have it appear more transparent/translucent.

Lastly, we learned how to use Autodesk Maya to model several of the objects that we will have in our scene, such as the pumpkin, table, chair, etc.

<br>

## Preliminary Results
#### Wind
We first added wind simulation by modifying `Cloth::simulate` in `cloth.cpp`. The idea is to add wind to `external_accelerations`, similar to adding the impact of gravity. Wind is defined as a force that acts on the cloth.

In the loop where the point mass positions are updated at each time step, we use the following formula below to calculate wind force which is then added to `pointMass.forces`.

$$
F_{\text{wind}}(i,j) = C_{\text{wind}} [n_{i,j} \cdot (v_{\text{wind}} - v_{i,j})] n_{i,j}
$$


- $$F_{\text{wind}}(i,j)$$: Force of wind at position $${(i,j)}$$
- $$C_{\text{wind}}$$: Constant that changes overall wind force
- $$n_{i,j}$$: Normal with `pointMass.normal()`
- $$v_{\text{wind}}$$: Velocity of the wind
- $$v_{i,j}$$: Velocity of the object at position $${(i,j)}$$

![pumpkin](/assets/img/milestone/wind.gif){:style="display:block; margin-left: auto; margin-right: auto; width:50%;"}

#### Ghost Cloth
- Blinn Phong Shader
    - Coefficient changes:
        - Diffuse: No change (wanted to keep the white color)
        - Ambient: Changed to `0` so that the base color is black
        - Specular: Increased it
    - Increase density in GUI to `30 g/m^2` to make it slightly heavier
    - Decrease `k_s` to `500 N/m` for a tighter spring: 
- Bump mapping: Downloaded a pic of a bed sheet to mimic the nature of a thin sheet without having to render each fiber
- Extra parameters
    - Used this [article](https://manual.keyshot.com/manual/materials/material-types/advanced-material/) to learn about different material types and as a baseline of what to have the different values equal to
        - Sheen: Color of our reflection
            - Set to lighter shade of white to appear brighter
        - Roughness: Set high since we wanted light to be evenly spread
        - Backscatter: Light scattered throughout the entire object
            - Provides soft effect
        - Edginess: How far the sheen spreads across the surface
            - Set it high to show brighter borders on surface edges (drastic fade)
- Changed the length of the cloth to be longer and resemble the shape of a ghost
- Fog/smoke
    - Attempted adding near the ghost's cloth to create a more ethereal visual by modifying `Custom.frag` (not successful) based on this [article](https://vicrucann.github.io/tutorials/osg-shader-fog/)

#### Modeling Additional Objects in Scene
- Modeled pumpkin, table, chair, candle, teddy bear, cello, fox, and a toilet in Autodesk Maya
- Need to import models and update codebase so it integrates with the sphere and cloth collision (ghost)

#### Adding Textures
- Started working on the flickering flame, which will be the shader used on the candle's flame in the scene
- Took inspiration from Shadertoy

<br>

## Reflection
Overall, we thought that our ghost cloth appearance is realistic and that the wind effect works well, but there’s a couple of issues with our "ghost" model and signficant details that we'd like to incorporate later on.

Incorporating wind was challenging and fog was especially difficult as well. There are a couple of ideas we have surrounding fog but we're not really sure the best way to approach them.

For modeling, we had to consider how the shader would be overlaid onto the model which made the overall appearance of the pumpkin less detailed than we wanted to, however this is subject to change.

Our biggest hurdle is figuring out how to integrate our models with our current "ghost" collision (consists of a sphere and plane). We recognized that these two objects were able to be in the same scene because they are different `.json` files under `/scene` but this is tricky to implement with the models we created on Autodesk Maya since they will be converted to `.dae` files. We will be going to office hours to get help on this :').

<br>

## Next Steps
We are a tiny bit behind schedule for our initial timeline since there were some obstacles that left us stumped for a longer duration than intended. 

Below are the items we intend on completing:
- Generate fog/smoke surrounding the ghost's cloth
- Add ghost face to the cloth
- Integrate all objects into one scene (import models and update existing codebase)
- Refine textures and shaders within all objects
    - Ex: Wax dripping, flickering candle light casting shadows to the surrounding objects

Stretch Goals:
- User interaction with scene (ex: functionality to move the ghost)
