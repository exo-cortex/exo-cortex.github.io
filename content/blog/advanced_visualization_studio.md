---
title: "advanced visualization studio"
date: 2021-05-30T11:35:18+02:00
draft: false
tags: [avs, visuals, procedural, art]
---

A looooong time ago - 2006*ish* - I used **AVS** (Advanced Visualization Studio - a music visualization plugin that came with **Winamp**) to create nice visualizations of the music that was being played. AVS is a little programming environment that compiles your code everytime you change something. It was actually the first contact with coding I had. A very sparse community of coders around the world made very nice visualization *presets*. 
Unknowingly I came into contact with a lot of concepts that I would later learn the names of in my physics studies. In AVS I dealt with *vector fields*, *numerical integration* via the euler-method, *matrix-multiplications* (for rotations), *bezier-curves* [1], *reaction-diffusion-systems* and (somehow related) *phase-oscillators* which later became central in my bachelor- and master-thesis. 

{{< video src="/video/trip.webm" type="video/webm" preload="false" width="200" >}}
{{< video src="/video/try_one.webm" type="video/webm" preload="false" width="200" >}}
{{< video src="/video/disco.webm" type="video/webm" preload="false" width="200" >}}

<!-- {{< video src="/video/out.webm" type="video/webm" preload="false" width="600" >}} -->

Currently **Grandchild** is working at updating the ancient AVS source code. The idea is to make it compatible with modern compilers like GCC (with all their optimizations) and free it of its windows dependencies. Later it might even run in the browser where it might be (re-)integrated into the online Winamp player [webamp](https://webamp.org/). Ideally AVS could run even faster than it did 20 years as it could be optimized further or even run on a modern graphics cards. 

[1] - my friend [**Grandchild**](https://github.com/grandchild) implemented *bezier-curves* into a preset which I then modified to draw a swarm of colorful lines each responding to its own spectral band in the music.

