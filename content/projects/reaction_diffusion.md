---
title: "reaction_diffusion_systems"
date: 2021-05-30T12:46:17+02:00
draft: false
math: true
---

{{< figure src="/img/reaction_diffusion_crop.svg" title="a typical reaction-diffusion pattern." >}}

Reaction-diffusion systems can model many natural pattern-forming processes. 

One very popular reaction-diffusion system is the **Gray-Scott** model, which consists of 2 coupled partial differential equations:
$$ 
    \frac{\partial u}{\partial t} = r_u \nabla^2 u - u v ^2 + f(1- u)
$$
$$
    \frac{\partial v}{\partial t} = r_v \nabla^2 v + u v ^2 - (f + k) v
$$

{{< video src="/video/react_anim_01_compatible.webm" type="video/webm" preload="auto" width="200" >}}

In this model the interaction of 2 chemicals $u$ and $v$ with their respective diffusion rates $ r_u$ and $r_v$ is defined. The parameters $f, k$ are system-specific. Think of $u$ and $v$ as two densities distributed over a domain. In my case this domain is a 2-dimensional area. Which means that $u$ and $v$ are simply 2 textures.

<!-- <video  src="video/react_anim_01_compatible.webm"></video> -->
