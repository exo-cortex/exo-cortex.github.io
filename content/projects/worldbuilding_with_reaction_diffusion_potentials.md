---
title: "worldbuilding_with_reaction_diffusion_potentials"
date: 2021-07-01T20:51:54+02:00
draft: false
tags: [worldbuilding, reaction-diffusion, idea]
tldr: a worldbuilding idea that would create 3D-landmasses with weird shapes.
math: true
---

For at least 5 years I have developed this idea in my head and pondered about ways implement it. Here I will try to at least describe it so that I can at least communicate it.  

## 1. changing the way mass accumulates.

**"Mass tells space-time how to curve, and space-time tells mass how to move."** *John Wheeler*

In out universe there is a **bi-directional** relationship between mass and space. Both influence each other: Mass creates a potential $V(x,y,z)$ which is defined for each point in space and the gradient of the potential $\nabla V$ tells us in which direction gravitational pull is moving this mass. The gravitational pull is the force which accelerates mass towards areas that are deeper in the potential well. This leads to the mass distribution that we know - mostly concentrated in stars or planets that are round.

I thought - why not break this two-way interaction and simply define an arbitrary potential-function $ V: \R^3 \rightarrow \R $ ourselves? 
We all (probably) know this visualization of gravity with a [rubber-sheet](https://www.youtube.com/watch?v=MTY1Kje0yLg) and a heavy ball. The weight of the ball bends the rubber downwards forming a potential $ V \propto 1/r$ (more exactly a function $V(x,y) = - 1 / \sqrt{ (x - x_m )^2 + (y - y_m)^2 }$ with $(x_m, y_m)$ describing the position of the mass object. The slope of the rubber-sheet (meaning the derivative - or gradient of the function V(x, y) tells us in which direction the gravitational pull is. So if we put another smaller ball onto the sheet it moves towads the first mass or circles around it. The problem with this visualization is of course that the the height of the rubber-sheet isn't really in the third spatial dimension. This example is still only 2D. We simply need the third dimension to plot the potential of each (x,y)-coordinate. We can only visualize the 2D-version of this, because in three dimensions we would need a 4th axis to plot the potential.
If we now define a _random_ potential-function in our world environment and place mass-particles everywhere the gradient from the potential would lead to mass to accumulate and fill in the lower places of the potential. Like Water that is filling lower places of a terrain. Since we switched off the "mass-curves-space"-interaction mass isn't capable of changing the potential itself.

Now If we define a function in 3D-space we can do the same thing: distribute particles evenly and let them "fill" the places of low potential. This would lead to 3-dimensionsl "scructures" of mass and surfaces. It would also lead to gravitational pull (or simply a "down" direction).

## 2. using reaction-diffusion-systems to create the potential.
You have probably seen reaction diffusion systems - here are a few of them (pictures on the site) https://karlsims.com/rd.html . They are often stylized as black and white. But in reality they are greyscale. there is simply a cut made with everything below a brightness value being made black and the rest is white. So in 2D the greyscale value can be seen as a potential value. Depending on the system parameters the reaction diffusion system can result in many different "shapes". They can be long spaghetti, little regularily-spaced drops, or finger-print-like shapes. For me the really cool reaction diffusion systems are the ones defined in 3D (see -> https://c1.staticflickr.com/5/4143/4901432173_3567be4f20_b.jpg and https://www.youtube.com/watch?v=ixs_j6dRPbk ). Depending on the system parameters they can be again drops, spaghetty, or (as in the image) weird bended surface-like structures. (Note: with 3D-reaction diffusion system I do NOT mean visualizing the potential of a 2D reaction-diffusion system in the third dimension - although this is also nice.)

So in essential this could be used to create (game)-worlds that would differ greatly from the usual planet shapes. The landmasses would be simply distributions on 3D space. But they would be locally flat. The gray-scott reaction diffusion system is fairly simple. There are more complicated systems which can have a hierarchy of structures - like a macro-scructure and more finer micro-structures (like weird shaped mountains or even things like floating rocks (like in avatar)).

## 3. slowly changing the potential over time
The coolest aspect for me about the idea of having an underlying potential function that is resulting in this mass-accumulation is that the potential-function can be slowly changing. This could result in something like tektonics, earthquakes and similar things. If mass would accumulate in certain areas one could imagine that it would after some time "bake" into a certain shape. Think like sediments or clay on the ocean floor that after millions of years forms sandstone which cannot bend. So If the underlying potential is slowly changing the mass cannot immediately follow which produces stress that will be released in sudden shifts - like earth-quakes. Only that it is probably not "plate"-tektonics. These tektonics might be used to create mountains or something similar.

## 4. varying the system parameters over the spatial domain
The system parameters which determine in the emergence of e.g "spaghettis", "drop", fingerprints or spirals can be changed locally. Meaning that the same system creates spaghetties in one area and droplets in another one. This varying of parameters could be used to create different kinds of environmants or "landscapes". There could be areas of roughtly aequidistant (maybe rather isolated?) free floating drops (or mini-planets) that slowly change into short and then longer sphaghettis until most of the landmasses are connected. For a 2D-version of varying system parameters see here: https://mrob.com/pub/comp/xmorphia/


## 5. [**Extra**] additional effects could be explained (kind of) understandable. (worldbuilding)
The potential function can vary drastically and suddenly. Our Earth's potential well is locally very smooth - the force of gravity is not changing much. E.g. there is a very very tiny measurable difference in gravity on the top of Mt Everest, but it is almost non-existend. With an arbitrary potential function this does not need to be.
So there could exist or emerge areas where the potential suddenly gets _incredibly_ deep - resulting in sudden very strong increases of gravitational pull. If something like this appears in the "sky" (meaning an area where no land mass exists) the gravitational pull could be so strong that dust and/or air molecules would accumulate or even fuse together because they would suddenly accelerated so strongly that fusion (or fission) would be possible. This could make "stars" possible (little areas that appear and dissappear where suddenly accelerated particles collide with each other.
Another potentiallyweird idea I had was this: If something is "deep" in the potential well it could be seen as being "near" in a forth dimensional direction where it is near some kind of energy-source. Energy could "tunnel" to areas in these deep wells and heat them up. This way volcanic activity could be explained.
If sudden very deep potential-holes/ or -trenches exist under the earth they could explain the creation of various types of stones or elements that would otherwise only form under different pressure environments. 

## 6. notes
The whole 3D-Landmass would probably be nice as a number of voronoi-3d-cells. (the 3d-analogon of voronoi cells). What I find so interesting about this: If there was a strategy-game played on this environment things like "what is the closest way" from A to B would be rather unintuitive. Note that the landmass could have oceans, lakes and rivers on it complicating the whole affair. I even thought about a strategy game where one faction could use resources to "dig to the other side" of an area and therefor create a sudden advantage. From a worldbuilding perspective the job of the "map-maker" would be a rather important and very prestigious one.
Some things I have thought about but will spare for another time: Where does the "sun" come from? Will there be a day-night-cycle? How does 3D-weather work? Will there be seasons?

If you have questions or further ideas, send me a message! (see about-page)

---
some tools that might be useful for implementing this:
- [voro++](http://math.lbl.gov/voro++/) 3-dimensional voronoi tesselation library