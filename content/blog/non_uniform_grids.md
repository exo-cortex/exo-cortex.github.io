---
title: "non_uniform_grids"
date: 2021-06-11T12:21:02+02:00
draft: true
math: true
---

I am fasctinated by non-uniform grids. They are irregular, but we can still do a lot of things with them.
Wikipedia has a nice overview of the different [types of meshes](https://en.wikipedia.org/wiki/Types_of_mesh). 
With kartesian grids we do not have to remember the position of each grid point, as they are defined by a simple rule. For example in 2 dimensions a grid point in row $i$ and column $j$ has the coordinate 
$$
    \mathbf{r}_{i,j} = \Delta_x \begin{pmatrix} i \\\\ 0 \end{pmatrix} + \Delta_y \begin{pmatrix} 0 \\\\ j \end{pmatrix} + \begin{pmatrix} x_0 \\\\ y_0 \end{pmatrix} 
$$
with $\Delta_x$ and $\Delta_y$ being the grid constants and $x_0$ and $y_0$ being offsets by which the grid is shifted.

## irregular grids

With irregular grids we have to give up concepts like *rows* and *columns*. The grid simply becomes a list of all the points with their coordinates

$$  \mathbf{r}_1 = (x_1, y_1) $$
$$  \mathbf{r}_2 = (x_2, y_2) $$
$$  \vdots $$
$$  \mathbf{r}_1 = (x_1, y_1) $$
$$  \mathbf{r}_1 = (x_1, y_1) $$