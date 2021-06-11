---
title: "advanced visualization studio"
date: 2021-05-30T11:35:18+02:00
draft: false
tags: [avs, visuals, procedural, art]
hovervideo: true
---

A looooong time ago around **2006** I began using **AVS** - [Advanced Visualization Studio](https://en.wikipedia.org/wiki/Advanced_Visualization_Studio) which came with the famous Winamp Media player. Winamp came with 2 visualization plugins - Milkdrop and AVS. The music visualizations used input from the music to create procedural art. The user could choose from a variety of *presets*. With AVS users could create their own presets, because AVS is its own little programming environment. As it compiles your code everytime you change something changes to the code can be seen in realtime. For me it was the first ever contact with coding that I had. A very sparse community of coders around the world made very nice visualization presets and discussed them. Since every preset would present its contents openly, everyone could simple change parameters of a given preset and thereby transform it - making a **remix** of a preset. This made possible that many presets would be remixed versions of previous ones. When presented with some mysterious code fragment, the user could simply change it and in realtime see the effects of this change. I used this approach a lot to reverse-engineer incomprehensible code. Unknowingly at the time I came into contact with a lot of concepts that I would later learn the names of in my physics studies: 
In AVS I dealt with 
- vector fields
- numerical integration via the euler-method
- matrix-multiplications (for rotations)
- bezier-curves [1]
- reaction-diffusion-systems [2]
- phase-oscillators [3]

Below are a few short examples (without music) of what AVS could look like.

{{< video src="/video/trip.webm" type="video/webm" preload="false" width="200" >}}
{{< video src="/video/try_one.webm" type="video/webm" preload="false" width="200" >}}
{{< video src="/video/disco.webm" type="video/webm" preload="false" width="200" >}}

<!-- {{< video src="/video/out.webm" type="video/webm" preload="false" width="600" >}} -->

An AVS-preset is a list of effects that manipulate an input image in order to create an output image. For each frame AVS works through the list of effects.

Currently **Grandchild** is working at updating the ancient AVS source code. The idea is to make it compatible with modern compilers like GCC (with all their optimizations) and free it of its windows dependencies. Later it might even run in the browser where it might be (re-)integrated into the online Winamp player [webamp](https://webamp.org/). Ideally AVS could run even faster than it did 20 years as it could be optimized further or even run on a modern graphics cards. 

[1] - my friend [**Grandchild**](https://github.com/grandchild) implemented *bezier-curves* into a preset which I then modified to draw a swarm of colorful lines each responding to its own spectral band in the music.

[2] - see my post about [reaction diffusion systems]({{< ref "/projects/reaction_diffusion.md" >}})

[3] - somehow related to [2] - phase oscilators became central in my bachelor- and master-thesis 
