---
title: "oval_relatives"
date: 2021-05-31T11:15:00+02:00
draft: false
math: true
---

{{< figure src="/img/cuve__thing_dark.svg" title="[1] this shape is neither round nor oval." >}}

A few years back I experimented with shapes that are *almost* round, but not quite yet. Imperfections that become irritations are very interesting for me. Imagine a round mirror, or a picture frame shaped like the object [1] above; would you immediately see that it isn't round? Most people would expect it to be round or oval and find it to slightly deviate from the norm. 

### 1. the basic shape

The basic shape - the edge of the red area - is described by

$$
\mathbf{v}(\phi) = \begin{pmatrix}x(\phi) \\\\ y(\phi) \end{pmatrix} =  \overbrace{(1 + f(\phi))}^{\text{radius}} \times \underbrace{\begin{pmatrix} \sin(\phi) \\\\ \cos(\phi) \end{pmatrix}}_{\text{unit circle}}.
$$

with $\phi \in \[0,2\pi\]$. If $f(\phi) = const$ i.e. $f'(\phi) = 0$ the shape $\mathbf{v}(\phi)$ becomes a perfect circle. If we now make the deviation of the radius a (small) function over $\phi$, we can simply create a shape like the one above. In my case I wanted to the deviation $f(\phi)$ to be a simple [**Fourier series**](https://en.wikipedia.org/wiki/Fourier_series) of only few components:

$$
    f(\phi) = \sum_{i=1}^{N} a_i \sin(i\phi) + b_i \cos(i\phi)
$$
Alternatively we can describe $f$ as a sum of only sine-functions, each with its respective phase-offset $\theta$:
$$ f(\phi) = \sum_{i=1}^{N} a_i \sin(i\phi + \theta_i) $$

### 2. offset curves

Graphic designers already now the concept of an "offset curve", known in math as a [parallel curve](https://en.wikipedia.org/wiki/Parallel_curve). If we draw parallel curves outside or inside our curve $\mathbf{v}$ we can make beautiful parallel curves $\mathbf{v}_1, \mathbf{v}_2, ...$. The outer dark curve in [1] is such a parallel curve derived from the edge of the red shape.

To make things short, given the two functions $x(\phi)$ and $y(\phi)$ describing the $x$ and $y$ coordinates of a curve $\mathbf{v}(\phi)$ we can define the parallel curve $\mathbf{v}_d(\phi)$ with offset $o$ as

$$ 
    \mathbf{v}_d(\phi) = \mathbf{v}(\phi) + d \times \overbrace{\begin{pmatrix} \frac{ y'(\phi)}{\sqrt{x'(\phi)^2+y'(\phi)^2}} \\\\ \frac{ y'(\phi)}{\sqrt{x'(\phi)^2+y'(\phi)^2}} \end{pmatrix}}^{\text{orthonormal vector}}.
$$

In words: We follow the original curve $\mathbf{v}$ and at each point we go into the direction orthonormal - i.e. orthogonal/perpendicular _and_ normalized to unit length of $1$ - to the tangent of the curve at that point.

---

**todo**:
- animation: wabbelgifs, increasing length of the series. 