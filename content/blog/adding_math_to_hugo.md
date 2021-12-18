---
title: "adding math to hugo"
date: 2021-05-26T18:47:06+02:00
draft: false
math: true
tags: [hugo, math, LaTeX]
---

with the help of this nice [**explanation**](https://mertbakir.gitlab.io/hugo/math-typesetting-in-hugo/) I was able to add math-typesetting to my blog. The framework is **KaTeX** and it supports a [variety](https://katex.org/docs/supported.html#sqrt) of **LaTeX** math typesetting.

This enables me to write fomulas like these:

$$
    z_{i}(t) = (\lambda + i\omega + \gamma |z_{i}(t)|^{2})z_{i}(t) + \sum_{j=0}^{N} \kappa_{i\leftarrow j} e^{i \phi_{i \leftarrow j}}z_{j}(t - \tau_{i\leftarrow j}) 
$$

It also allows to write math symbols like $\infty$ within text. This is pretty cool for things like $\tfrac{1}{3}$.