----
In the 2 dimensional case, the total curvature of a closed plane curve is always equal to $2\pi$ times its turning number. as:
$$\int _{0}^L \kappa \, ds = 2\pi k $$
The total gaussian curvature is always $2\pi$ times its Eular characteristics, which is defined as the number of genus, as: $$\mathcal{X} := 2-2g$$
- $g$ is the number of genus

And the theorem says that $$\int _{S} K\, dA = 2\pi \mathcal{X} $$
For surfaces with Boundaries, the theorem is defined as: $$\int _{S} K \, dA + \int _{\partial S}  \kappa_{g}\, ds = 2\pi \mathcal{X}, \mathcal{X} = 2-2g - b $$

## Discrete Gauss-Bonnet Thorem

The Gauss-Bonnet Theorem (Discrete Version) over a 2 dimensional simplicial complex manifold is the following relationship, where: $$\sum_{v\in V} d(v) = 2\pi\mathcal{X}$$
- $d(v)$ stands for the angle defect of the vertex
- $\mathcal{X} = |V| - |E| + |F|$ is the Euler characteristic of the surface

The angle defect is defined as follows: $$d(v) = 2\pi - \sum _{f\in F_{v}} \angle_{f}(v)$$
- $f$ represents the faces (2-simplex) that includes the vertex $v$.




