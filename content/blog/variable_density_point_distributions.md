---
title: "variable density point distributions"
date: 2021-06-28T14:43:57+02:00
draft: false
math: true
---

![a distribution of dots](/img/points_wave.svg)

I *finally* implemented my own version of the poisson disk sampling algorithm[^1]. The standard algorithm places points on a finite 2D plane with a minimum distance $d_{min}$ between them until there is no more space for additional points. The distribution of the distances of adjacent points is a poisson distribution - hence the name. Robert Bridson described an efficient algorithm to create these samplings[^2]. It uses a grid to store the points in them. This way every new candidate point need only check adjacent grid cells for existing points that might be closer than $d_{min}$ - no need to check every single prior point. If no existing points are too close the candidate becomes a new sample point.
 
In my case I wanted to make the minimum distance adjustable, thereby varying the point density (see image above). The original method of saving points in a background grid does not work, as the grid has to be finer in some and coarser in other areas. A quadtree[^3] is ideal for this. I tried to implement my own quadtree in C++, but got impatient unfortunately. Instead I opted to implement it in python first and maybe later recreate a faster version in C++ or Rust. I found a nice quadtree implementation in python [^4] and added a method that checks if there is *any* point in the quadtree that is closer than $d_{min}$ to an input point.

The algorithm is sketched beneath:

```python
import random
from quadtree import Rect, Quadtree


domain = Rect(0, 0, width, height)
number_of_candidates = 25

qt = QuadTree(domain)

first_point = (width / 2, height / 2)
points_list = [first_point]
qt.insert(first_point)

active_points = [0] #stores indices of points in points_list that can be used to spawn new points near to them
point_counter = 1

while (len(active_points) > 0):
    point_counter += 1
    current_index = random.choice(active_points)
    current_x, current_y = points_list[current_index]
    minimum_radius = some_function(current_x, current_y)
    for i in range(number_of_candidates):
        candidate_point = make_candidate(points_list[current_active].x, points_list[current_active].y , minimum_radius)
        if not qt.is_too_close(candidate_point) and domain.contains(candidate_point):
            qt.insert(candidate_point)
            points_list.append(candidate_point)
            active_points.append(point_counter)
            break
    else:
        active.remove[current_index]

```

The deviation from the standard algorithm is that $d_min$ depends on the $x$ and $y$ coordinate of the active point. The point distribution uses the following function:
```python
base_radius = 10

def some_function(x , y):
	r = math.sqrt((x - 1.5 * width/2) ** 2) + ((_y - height/2) ** 2))
	return base_radius * (1.25 + math.cos( r * 0.075))
    # varies between 0.25 and 2.25 times base_radius
```

The function to create new candidate points is simply creating a random point within the annulus region around the current active point:
```python
def make_candidate(anchor_x, anchor_y, minimum_radius):
    angle = random.uniform(0, 2.0 * math.pi)
    distance = random.uniform(1.0, 2.0) * minimum_radius
    x_coordinate = anchor_x + distance * math.cos(angle)
    y_coordinate = anchor_y + distance * math.sin(angle) 
    return (x_coordinate, y_coordinate)
```

I find these images highly interesting. They consist of only individual elements, yet collectively they can mimic continuous gradients from bright and dark areas.

---
[^1]: [Poisson disk sampling](https://en.wikipedia.org/wiki/Supersampling#Poisson_disk)
[^2]: [Fast Poisson Disk Sampling in Arbitrary Dimensions](https://www.cct.lsu.edu/~fharhad/ganbatte/siggraph2007/CD2/content/sketches/0250.pdf)
[^3]: [quadtree](https://en.wikipedia.org/wiki/Quadtree)
[^4]: [quadtree in Python](https://scipython.com/blog/quadtrees-2-implementation-in-python/)

more images:
![a distribution of dots](/img/points_wave_diagonal.svg)