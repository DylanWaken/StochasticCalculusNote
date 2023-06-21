-----
This chapter dependes on [[Smooth Curves]]

A discrete curve is a piecewise linear parameterized curve, as a continuous map of a sequence of points on a range to points in $\mathbb{R}^n$ connected by straight line sequence.

In more common fassion, a discrete curve is determined by a discrete $\mathbb{R}^n$-valued 0-form $\gamma$ on a oriented manifold (abstract simplicial 1-complex), as $$\gamma(v_{0}) : \mathbb{R}\to \mathbb{R}^n$$
We can have a smooth curve from discrete curves using hat functions.

The differential of the curve in the discrete case is defined as the differenced between the vertices in the target space, as: $$(d\gamma)_{ij} = \gamma_{j}-\gamma_{i}$$
The discrete unit tangent vectors on the edges (excluded vertices) can be calculate the same way is smooth curves, as we have the relationship: $$T_{ij} = \frac{(d\gamma)_{ij}}{\lvert (d\gamma)_{ij} \rvert }$$
Exactly the same with respect to the continuous case:

![[Screenshot from 2023-04-13 15-13-53.png]]

The unit normal is also defined the same in the 2d case, as we rotate by 90 degrees conter clockwise, as:
$$N_{ij} = \mathcal{J}T_{ij}$$
