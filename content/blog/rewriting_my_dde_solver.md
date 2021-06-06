---
title: "rewriting_my_dde_solver"
date: 2021-05-29T20:03:12+02:00
draft: false
---

In the final months of writing my master thesis there was little time. Simultaneously a lot of problems in the c++ code that I had written became very apparent. Since then it has been a dream of me to rewrite the whole thing. Thereby learning even more C++ and also using git/github in a more professional manner (I used it before, but only locally and I didn't quite adhere to a consistent way of commiting changes or wording the commit messages). 

My rewrite can be found [here](https://github.com/exo-cortex/dde_network_solver/) on my github. The goal will be to reimplement the features of the old solver, but in a more modular and flexible manner. The features of the old DDE solver were:
- construction of networks as a collection of edges with individual coupling weights, phases and delays
- implementation of the [Stuart-Landau system](https://en.wikipedia.org/wiki/Stuart%E2%80%93Landau_equation)
- integration of the delay-coupled systems with runge-kutta 4th order method
- analysis of the timeseries - finding extrema 
- saving timeseries in a simplified manner to dramatically save space [**RDP**] 
- measuring (non-)linear reservoir computing performances via Legendre-Polynomials [**DAM12**]

Additional features that shall be in the new solver:
- adaptive refinement of the parameter space when scanning
- implementation and easy changing of advanced dynamical systems e.g. **Lang-Kobayashi**, **Lorenz-sytem**, **Rössler-System** and more.

---
[**RDP**] using the [Ramer-Douglas-Peucker algorithm](https://en.wikipedia.org/wiki/Ramer%E2%80%93Douglas%E2%80%93Peucker_algorithm)


[**DAM12**] *Dambre, J., Verstraeten, D., Schrauwen, B. et al.* **Information Processing Capacity of Dynamical Systems**. Sci Rep 2, 514 (**2012**). https://doi.org/10.1038/srep00514