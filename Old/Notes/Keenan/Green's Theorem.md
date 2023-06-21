----
## Green's Theorem

Green's theorem works on the curves in a 2 dimensional x-y plane

The line integral over a vector field is defined as the following: 
$$\int _{C} \vec{F} \cdot\, d\vec{r} = \lim_{ \Delta r \to \infty } \sum_{i=1}^n F(r_{i}) \cdot \Delta r_{i}$$
- $\vec{ F}$ is the vector field that we are integrating over the curve
- $r$ is the parameterized curve around the region

If we have $r$ parameterized as $r(t)$, we have:
$$\int _{C} F(r) \cdot \, dr  = \int _{a} ^b F(r(t)) \cdot r'(t)\, dt $$
What we mean here is the measure of the total "vector divergence" from the integrated direction along the curve. Another way to understand is the total "work" the vector field applied on the curve. The more divergent the vector is against the curve direction, the greater this integral will be. 

The easy outcome of this idea is that, if vector is tangent to the curve at a point, the line integral would evaluate to zero at the point. In other cases, only the normal component of the vector field along the curve would contribute to the curve integral.

Green's theorem states the line integral over a closed loop (in the counter clockwise direction) around simple region $S$ is equivalent to the total curl of every points in the region: 
$$\int _{\partial S} \vec{F} \cdot\, d\vec{r}  = \iint_{S} \nabla \times \vec{F} \,dA$$
- $\partial S$ stands for the boundray around the region

Normally curl is only defined in the third dimension, but note that in the 2-dimension space curl is the 90-degree rotation of the divergence, so the 2d curl can be defined as well.

If we have the 2-dimension vector field defined as:
$$F(x,y) = \begin{bmatrix}
P(x,y) \\
Q(x,y)
\end{bmatrix}$$
Then the green's theorem evaluates to the following form:
$$\int _{\partial S} P  \, dx + Qdy = \iint _{S} \left( \frac{{\partial Q}}{\partial y} - \frac{{\partial P}}{\partial x} \right) dA$$
The proof of this theorem is not hard. Note that since line integral is directional related, if we separate the region $S$ into $S_{1}$ amd $S_{2}$, the line integral of $S$ would be the sum of both line integrals, as:
$$\int _{\partial S} \vec{F}  \, d\vec{r}  = \int _{\partial S_{1}} \vec{F}  \, d \vec{r} + \int _{\partial S_{2}} \vec{F}  \, d \vec{r}$$
The reason for this fact is that, the shared edge of the sub regions canceled out since they are on opposite directions.

![[Screenshot from 2023-03-24 22-06-59.png]]

Now, if we segregate the region of integrals into infinitely small square regions, the line integral would evaluate the little change of the direction the vectors are pointed on the boarders (since the parts of the same vector direction would be canceled out). And therefore, what we get is the curl of the point, or the tendency of "rotations" of the vector field around a point. 

we can estimate the line integral of the infinitely small region as the curl of the point, as:
$$\int _{\partial S_{r}}  \vec{F} \, d\vec{r}  \approx \nabla \times \vec{F} |r|$$
And by apply this replacement to every point in the region, we have the structure of the green's theorem. Note that this "proof" is just an intuition instead of a clear and careful proof.

## Stoke's Theorem

Stoke's theorem is extremely similar to the green's theorem, but it generalizes to any 2d surface in the 3 dimensional space. the main region of application is surface integrals.
$$\iint _{S} f(x,y,z) dS$$
Which, like line integrals, we are confining the result of the integral over a surface in 3 dimensions. 

We consider the surface $S$ to be parameterized with variables $$S(s,t)$$
And the parameterization would also give us the "direction" of integration in the surface.

The surface integral over a 3 dimensional vector field follows the same principle, as only the normal component to the surface of vectors on the surface would contribute to the surface integral. and therefore, we have:
$$\begin{align}
\iint_{S} F \cdot dS &= \iint_{S} (F \cdot n) dS \\
&= \iint _{T} \left( F(S(s,t)) \cdot \frac{{\frac{{\partial S}}{\partial s} \times \frac{{\partial S}}{\partial t}}}{\lvert {\frac{{\partial S}}{\partial s} \times \frac{{\partial S}}{\partial t}} \rvert }\right) |{\frac{{\partial S}}{\partial s} \times \frac{{\partial S}}{\partial t}}| ds\, dt \\
&= \iint_{T} F(S(s,t)) \cdot (\frac{{\partial S}}{\partial s} \times \frac{{\partial S}}{\partial t}) ds \, dt
\end{align}$$
Note we can convert $dS$ to $|{\frac{{\partial S}}{\partial s} \times \frac{{\partial S}}{\partial t}}| ds\, dt$ using the rule of parallelogram area between vectors.

And now we can try to prove the stoke's theorem. The theorem states that for any simple closed region on the simple 2-dimensional surface, the following equation holds:
$$\int _{\partial S} \vec{F} \cdot\, d\vec{r}  = \iint_{S}( \nabla \times \vec{F} ) \cdot\,dS$$
Note that we are integrating over $dS$ instead of $dA$. If we have the unit normal vector on the surface that encodes this information, we would have the following transformation:
$$\iint_{S}( \nabla \times \vec{F} ) \cdot\,dS = \iint_{S}( \nabla \times \vec{F} ) \cdot\ \vec{n}\, dA$$





