---
title: "advanced visualization studio"
date: 2021-05-30T11:35:18+02:00
draft: false
tags: [avs, visuals, procedural, art]
hovervideo: true
---

A looooooong time ago in the year 2006 I began to play around with **AVS**. [Advanced Visualization Studio](https://en.wikipedia.org/wiki/Advanced_Visualization_Studio) came as a plugin with the famous Winamp Media player. Winamp had 2 plugins that rendered colorful procedural art that reacted to the music. These music visualization plugins were "Milkdrop" and "AVS". Typically the user would choose from a variety of *presets* that would then visualize the sound. 
But in AVS users could actually create their own presets. Besides using precompiled effects that can be combined at will, AVS is also its own little **programming environment** with its own programming language [eel](http://eelang.org/). As AVS compiles your code everytime you change it the results from that change can be seen in realtime. This immediate realtime-compilation made AVS a fantastic tool for experimentation. 

For me it was the first ever contact with coding that I had. A very sparse community of coders/artists around the world made very nice visualization presets and discussed them via the ancient [Winamp Forums](http://forums.winamp.com/forumdisplay.php?f=85). AVS presets were - and still are - a wonderful combination of programming and art. Different artists had very unique styles and esthetic expressions. Some presets were technically impressive, others were great from a design perspective. 
Since every preset would present its contents openly, everyone could simply change parameters of a given preset and thereby transform it - **remixing** other people's presets was a big thing. This made possible that many presets would be remixed versions of previous ones. The simplest way of learning how another artist made a certain effect was to play around with the preset, change parameters and observe the effects. The result of this playful interaction was usually a new remix. I used this approach a lot to reverse-engineer incomprehensible code. 

(Unknowingly at the time) I came into contact with a lot of concepts that would later reappear in my physics lectures: 
In AVS I dealt with 
- vector fields
- numerical integration via the euler-method
- convolutions
- matrix-multiplications (for rotations)
- bezier-curves [1]
- reaction-diffusion-systems [2]
- phase-oscillators [3]

Below are a few short looping examples (without music) of what AVS could look like.

{{< video src="/video/trip.webm" type="video/webm" preload="false" width="200" >}}
{{< video src="/video/try_one.webm" type="video/webm" preload="false" width="200" >}}
{{< video src="/video/disco.webm" type="video/webm" preload="false" width="200" >}}

<!-- {{< video src="/video/out.webm" type="video/webm" preload="false" width="600" >}} -->

## AVS today and tomorrow
AVS was never mainstream. It was significantly slower than its big brother "Milkdrop" and was therefor only suitable for low resolutions. But AVS made it possible to programm almost *anything*. The last version was released about 15 years ago and is thoroughly out of touch with modern processors, compilers and optimization methods. A few attempts have been made to update AVS, but most of them have been incomplete: Some effects that only exist as compiled binaries are not included in these versions. 

Currently Grandchild is working hard at [updating the ancient AVS](https://github.com/grandchild/vis_avs). The idea is to make it compatible with modern compilers like GCC and free it of its windows dependencies. Later it might even run in the browser where it might be (re-)integrated into the online Winamp player [webamp](https://webamp.org/). Ideally AVS could run even faster than it did 20 years ago as it could be optimized further or even run on a modern graphics cards. What is needed is an implementation of all its effects as shaders that can run on a GPU. Some effects are easy to implement, others might even be impossible. A major challenge is the missing source code for some of the effects. This made it necessary to disassemble certain binaries and comprehend it. Some of the more advanced effects use a lot of assembler which make them extra challenging. But Grandchild is slowly but surely progressing and has actually made it much further than previous attempts of updating this ancient and complicated piece of code. 

[1] - my friend [Grandchild](https://github.com/grandchild) implemented *bezier-curves* into a preset which I then modified to draw a swarm of colorful lines each responding to its own spectral band in the music.

[2] - see my post about [reaction diffusion systems]({{< ref "/projects/reaction_diffusion.md" >}})

[3] - somehow related to [2] - phase oscilators became central in my bachelor- and master-thesis 
