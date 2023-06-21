----
Intuitively, Curvature describes how a shape bends. It stands for how much do quantities differ from flat cases. 

The curvature of a arc-length parameterized plane curve can be described as the rate of change in the tangent with respect to the normal, as $$\kappa (s) := \left\langle  N(s), \frac{d}{ds} T(s)  \right\rangle $$
 Since the tangent is the first derivative of a curve, we can also write this as the second derivative of the curve mapping, where: $$\kappa(s) := \left\langle  N(s), \frac{d^2}{ds^2} \gamma (s)  \right\rangle $$
 For a plane curve, the curvature captures the notion of "bending", while for a space curve we also have another quantity of "torsion", which captures "twisting". $$\frac{d}{ds}\begin{bmatrix}
T \\
N \\
B
\end{bmatrix} = \begin{bmatrix}
0&-\kappa&0 \\
\kappa&0&-\tau \\
0&\tau&0
\end{bmatrix} \begin{bmatrix}
T \\
N \\
B
\end{bmatrix}$$
For a curve in a surface, it is decomposed into the **normal** and **geodesic** curvatures. 

![[Screenshot from 2023-04-17 21-33-27.png]]

## Curvature of a surface

THe Gauss map $N$ is a continous map taking each point on the surface to a unit normal vector. It can be visualized as a map from the domain to the unit sphere.

The **Weingarten map** $dN$ is the differential of the Gauss map $N$. At any point, $dN(X)$ gives the change in the normal vector along a given direction $X$ 

Since change in unit normal does not have any component in the normal direction, $dN(X)$ is always tangent to the surface. it is tangent to the unit sphere.

![[Screenshot from 2023-04-17 21-45-09.png]]

The region for $dN(Y)$ to be flipped is that, the surface bends in 2 different directions at the point.

Computing the Weingarten map has no different from computing the differential of a surface.

The **Normal Curvature** describes the rate the normal is changing for immersive surfaces along a given tangent direction. (like the direcitonal derivative).: $$\kappa_{N}(X) := \frac{{\langle df(X),dN(X) \rangle }}{\lvert df(X) \rvert^2 }$$
- It is equivalent of saying, we slice the surface in the tangent direction, and calculate the canonical curvature on the curve in that sliced plane.

Principle directions $X_{1},X_{2}$ are defined as the directions where normal curvature has minimum/maximum value (respectively). And the curvature at these directions are called Principle curvature.

- The priciple directions are orthogonal to each others ($X_{1} \perp X_{2}$) on the surface or $g(X_{1},X_{2}) = 0$

- The weingarten map at the principle direction $dN(X_{i})$ is the same as as the principle curvature multiplied by the tangent of the surface, where: $$dN(X_{i})= \kappa_{i}df(X_{i})$$
- Since the change in the unit normal $N$ is always tangent to the surface, there must be some linear map $S$ from tangent vectors to tangent vectors, called the **Shape Operator** as: $$df(SX) = dN(X)$$
-  The principal directions are in fact the **eigenvectors** of $S$, while the principal curvatures are the **eigenvalues** of $S$. This matrix is not symmetrical, which means the eigenvectors are only going to be orthogonal within the Riemannian metric.

We can solve for the shape operator using: $$df \circ S = dN$$
- Here $df$ and $dN$ are represented in their jacobian matrix form.

Umbilic Points are poitns where the principle curvatures are equal, and the principle directions are not uniquely determined. The shape operator might have repeated eigenvalues

We can use the **principle curvature network** (All directions for principle curves and directions) to assign a grid to the geometry. However, they might not works due to non-terminating tracing like spirals.

## Gaussian and Mean Curvature

The Gaussian curvature is defined as: $$K:=\kappa_{1}\kappa_{2}$$
Where the mean curvature is defined as: $$H:= \frac{1}{2}(\kappa_{1}+\kappa_{2})$$
Where $\kappa_{1}$ and $\kappa_{2}$ are the 2 principle curvatures.

![[Screenshot from 2023-04-18 21-14-34.png]]

Surfaces with $K>0$ are called convex surfaces
Surfaces with $K=0$ are called developable surfaces, as they can continuously transform into a plane without stretching or changing the length of the tangent vectors.
Surfaces with $H=0$ are called minimal surfaces, as they are in a saddle shape everywhere over the image of the surface mapping.

From the Intrinsic side, the gaussian curvature measures the deviation of the manifold from the euclidian space. It measure the ratio of area of a little ball around a point as it is embedded in the euclidian space and some arbitrary manifold. 

![[Screenshot from 2023-04-18 21-21-31.png]]






