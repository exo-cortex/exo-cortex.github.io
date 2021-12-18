---
title: "reaction_diffusion_systems"
date: 2021-05-30T12:46:17+02:00
draft: false
math: true
tags: [procedural, art, math, reaction-diffusion]
---

![raction diffusion pattern](/img/reaction_diffusion_crop.svg)

<!-- {{< figure src="/img/reaction_diffusion_crop.svg" title="a typical reaction-diffusion pattern." >}} -->

Reaction-diffusion systems can model many natural pattern-forming processes. 

One very popular reaction-diffusion system is the **Gray-Scott** model, which consists of 2 coupled partial differential equations:
$$ 
    \frac{\partial u}{\partial t} = r_u \nabla^2 u - u v ^2 + f(1- u)
$$
$$
    \frac{\partial v}{\partial t} = r_v \nabla^2 v + u v ^2 - (f + k) v
$$

In this model the interaction $u$ and $v$ can be seen as 2 chemicals each with their respective diffusion rates. $u$ and $v$ are simply two functions over some space (a 2D space in my case). $f, k$ are system-specific. We can think of $u$ and $v$ as two densities values distributed over a domain. In my case this domain is a 2-dimensional area. Which means that $u$ and $v$ are simply 2 textures.

{{< video src="/video/react_anim_01_compatible.webm" type="video/webm" preload="auto" width="200" >}}

![interesting pattern1](/img/little_creatures_800x800.png)
![interesting pattern2](/img/reaction_diffusion_mesh.png)

This animation was made with python using numpy and scipy. A version of the python-script can be found [here](https://github.com/exo-cortex/reaction_diffusion_python/).


---

see also:
- [reaction diffusion in the browser](https://pmneila.github.io/jsexp/grayscott/)
- [overview + classification of different patterns](https://mrob.com/pub/comp/xmorphia/pearson-classes.html)
