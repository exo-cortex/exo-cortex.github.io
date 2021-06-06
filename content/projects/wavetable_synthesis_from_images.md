---
title: "wavetable_synthesis_from_images"
date: 2021-06-02T13:43:48+02:00
draft: false
---

Any sound can become a tone if we repeat it very quickly. The repetition rate becomes the base-frequency of that tone. If we repeat the sample of a basedrum with **1 Hz** the base frequency is **1 Hz** - well below our hearing range. If we increase the repetition rate to **50 Hz** we can actually hear it. 

wavetable synthesis works by playing a very short audio sample on repeat. The repetition rate becomes the base frequency. Depending on the content of the sample the tone has a certain timbre. This way a synthesizer can recreate i.e. imitate the timbres of various instruments. 

The real potential of wavetable synthesis lies in the interpolation between different samples while the sound is generated. This way the sound is "morphing" and constantly transitioning from one timbre to the next. This morphing can be done slowly or quickly, rhythmically or continuous. Dubstep often made use of these sounds.

Usually audio synthesis software comes with a collection of pre-made wavetables. My idea use images and use the brightness values over time as the wavefunction. In the animation below the three color channels (R, G, B) of the well-known [Lenna](https://en.wikipedia.org/wiki/Lenna) image are shown on the left. A closed path is used to read the pixel's brightness values at each point of the path. On the right the brightness values are shown. Since the image has three color channels we can extract 3 wave forms. This could make it possible for us to gain stereo-sounds from a simple image. 

{{< video src="/video/lenna_circle.webm" type="video/webm" preload="auto" width="800" >}}