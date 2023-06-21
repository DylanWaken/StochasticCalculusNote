-----
## Planar curve

A **parameterized plane curve** is a map taking each point in an interval $[0,L]$ of the real line to some point in the plane $\mathbb{R}^2$

The **Differential of a curve** uses the fact that planner curves are $\mathbb{R}^2$-valued 0-form on an interval of the real line. The exterior derivative shows how vectors on the domain get mapped into the plane.

![[Screenshot from 2023-04-11 19-30-41.png]]

Note that this differential is not the unit tangent. The unit tangent of a parameterized curve is the map obtained by normalizing its first derivative as: $$T(s) = \frac{d}{ds} \gamma(s)/ \left\lvert   \frac{d}{ds} \gamma(s)  \right\rvert = d\gamma \left( \frac{d}{ds}  \right) /\left\lvert  d\gamma \left( \frac{d}{ds} \right)  \right\rvert $$
The differential, on the other hand, discribes for any arbitrary vectors on the 1 dimensional domain at a specific point, how it is going to be stretched into the curve.

Fof example, for a unit circle, the differential can be written as: $$d\gamma = \begin{bmatrix}
-\sin(s) \\
\cos(s)
\end{bmatrix}ds$$
Note that there exists reparameterization of the curve as $\eta : [0,L]\to[0,L]$ and the parameterized curves $\tilde\gamma(s) = \gamma(\eta(s))$ and $\gamma(s)$ stands for the same piece of geometry. Therefore, directly comparing meshes is extremely hard, since there can be arbitrarily many parameterizations for describing the same curve.

For curves, we have

- A parameterized curve is **regular** of the differential is nonzero everywhere. (this makes sure that the curve is differentiable and there exists no "sharp corners" as it can happen if the speed on the curve slows down to zero, making it differentiable but not smooth). 
- A curve is **embedded** if it is a continuous and bijective map from its domain to its mage, and the inverse map is also continuous. This property means that the curve does not intersect itself anywhere. The embedding preserves the topology,

For the planar curve, the unit normal can be expressed as the quarter-rotation $J$ of the unit tangent in the counter-clockwise direction: $$N(s):= JT(s)$$
The Curvature of a plane curve (arc-length parameterized) can be expressed as the rate of change in the tangent. As we can write the curvature as:
$$\kappa(s) := \left\langle  N(s), \frac{d}{ds}T(s)  \right\rangle $$ 
- Note that this is only true for the arc-length parameterized curve. It can be also written in the form of $$\left\langle  N(s), \frac{d^2}{ds^2} \gamma(s)  \right\rangle $$
Another fact is that for an arc-length parameterized curve, its shape is uniquely determined by its curvature. As it tells us how to "steer" along a path as we move at unit speed. 

Fron the other point of view, we can solve for a set of curves that has the same shape or same curvatures over its parameter. 

We first integrate curvature to get the angles of turning, as:regularly homotopic
$$\theta(s) := \int _{0}^s \kappa(t) \, dt $$
And then we can use this to solve for some unit tangent according to this angle, and finally integrate the unit tangents to get a curve, as:
$$\gamma (s) := \int _{0}^s T(t) \, dt $$
Note: this is theoritically possible, but analytically solving this is normally impossible

A **Turning number** $k$ is the number of counter-clockwise turns made by the tangent across the entire curve (only for closed curves). (This is called the topological decree of the map) It also encodes the direction of traversal along the curve, as.

![[Screenshot from 2023-04-11 21-09-49.png]]

For another rule, if the curve is arc-length parameterized, the turning number of the curve can be calculated as:
$$k = \frac{\theta(s)}{2\pi} = \frac{1}{2\pi} \int _{0}^s \kappa(t) \, dt $$
The **winding number** n is the number of times the curve "goes around" a particular point p, as:

![[Screenshot from 2023-04-11 21-48-26.png]]

A more accurate definition can be called as the total signed length of the projection of the curve onto a circle around the point.

A generalization of the quantities are: $$\begin{align}
&T(s) := {\frac{\gamma'(s)}{\lvert \gamma'(s) \rvert }}\implies k=\text{degree}(T(s)) \\
&\hat{\gamma}_{p}(s) := \frac{{\gamma(s)-p}}{\lvert \gamma(s)-p \rvert } \implies n = \text{degree}(\hat{\gamma}_{p}(s))
\end{align}$$
Here degree stands for the topological degree, and $\gamma_{p}$ is the projection of the curve onto a unit circle. The winding and the turning numbers

![[Screenshot from 2023-04-11 22-14-37.png]]

Note that winding numbers can be defined to be real numbers as "generalized winding numbers" for the estimation of noised / incomplete cuves/meshes. 

## Parameterized Space Curve

A space parameterized curve will be the mapping from a real range to points in $\mathbb{R}^3$, as:
$$\gamma:[0,L]\to \mathbb{R}^3$$
For any vectors on the real range $X(s_{1})$, the "mapped vector" to the curve can be found by applying the differential of the curve as: $$d\gamma(X(s_{1}))$$
To compute this using the basis 1-vector and basis 1-form, we can define: $$X:= \alpha\frac{ \partial}{\partial s}, \alpha:[0,L]\to \mathbb{R}, d\gamma = \left( \frac{{\partial x}}{\partial s}, \frac{{\partial y}}{\partial s}, \frac{{\partial z}}{\partial s} \right) ds$$
Note here on the left we define $X$ as some function that takes in locations on the range and produce a 1 dimensional vector 

And the application of the stretching of the vectors from $X$ by the curve mapping can be derived as: $$d\gamma(X) = \left( \frac{{\partial x}}{\partial s}, \frac{{\partial y}}{\partial s}, \frac{{\partial z}}{\partial s} \right) ds \left( \alpha\frac{ \partial}{\partial s} \right) = \alpha \left( \frac{{\partial x}}{\partial s}, \frac{{\partial y}}{\partial s}, \frac{{\partial z}}{\partial s} \right)$$
This is similar to the Jacobian matirx.

For a space curve, the equivalence of "curvature" is the "**torsion**" of the curve, meaning how fast the curve is twisting. It is like a "out of plane" bending.

For each point on the space curve, we can define a natural coordinate frame called the **Frenet frame** (which depends only on the local geometry). Its composed of 3 axis regarding a normal $N$, the tangent $T$, and another normal vector orthogonal to the normal as the binormal $B$.

![[Screenshot from 2023-04-13 11-41-59.png]]

In the plane case, we define unit tangent as the differential of the arc-length parameterized curve, and the unit normal as the "second derivative of the curve", or the derivative of the tangent with respect to curve parameter:
$$T = \frac{d}{ds} \gamma(s), N=\frac{d}{ds}T / \left\lvert  \frac{d}{ds}T  \right\rvert $$
By these two vectors, we can find the binormal as the cross product of the normals, as: $$B(s) = T(s)\times N(s)$$
The curvature and torsion can be found by the differentialtion of the Frenet frame in time, as: $$\frac{d}{ds}\begin{bmatrix}
T \\
N \\
B
\end{bmatrix} = \begin{bmatrix}
0&-\kappa&0 \\
\kappa&0&-\tau \\
0&\tau&0
\end{bmatrix}\begin{bmatrix}
T \\
N \\
B
\end{bmatrix}$$
- The conclusion of this theorm is that, the change in tangent defines curvature, while the change in the binormal define torsion.

In an other fassion, we can rewrite our definitions as: $$\kappa = - \left\langle  N, \frac{d}{ds}T  \right\rangle, \tau = \left\langle  N, \frac{d}{ds}B  \right\rangle $$
The fundamental theorem of space curves also applys here, as we can drive the arc-length parameterized space curve with curvature and torsion. This can be done through solving the system of ordianary differential equation. 

Note that, if the curve encounter a piece of straight line, the Frenet frame is not defined, since tangent is not changing over time and we have $\frac{dT}{ds} = 0$. We can only interpolate framse between the curved parts on the ends of this straight part.









