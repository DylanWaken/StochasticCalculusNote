----
**Local picture** discribes a surface through its the piecewise mapping and stretching of the surface from its original parameterized domain.

**Global Picure** is the collection of local pictures to discribe the surface as a whole instead of a piece.

These are also called an extrensic description as this system measures the geometry with the basis of the target space.

**Intrinsic picture** is the description of geometry independent from its embedding in the target space. it uses the **Riemannian metric** as the tool for description. 

## Parameterized Surface

A **Parameterized surface** is a map $f:U\to \mathbb{R}^n$ from a 2 dimensional region $U \subset \mathbb{R}^2$ into target space. There can exist many possible parameterizations for the same pair of domain and surface

An **Embedding** is a surface that preserves the topological properties of its domain. For a domain $U$, the embedding is a bijection onto its image $f(U)$ with a continouous inverse.

![[Screenshot from 2023-04-16 15-37-46.png]]

The differential of a parameterized surface tells us how then tangent vectors on the domain get "stretched out" into the space. More explicitly the differential of a surface is the exterior derivative of the parameterization. 

For the mapping: $f:U\to \mathbb{R}^3$, we can take the exterior derivatives as: $$df = \frac{{\partial f}}{\partial u} du + \frac{{\partial f}}{\partial v}dv$$
- Here $du$ and $dv$ are the basis 1-forms of the domain, and $\partial f / \partial u$ will be a vector valued function. The differential is technically a differential 1-form

And now, if we have a vector field defined upon the domain, as: $$X := a \frac{\partial}{\partial u} + b \frac{\partial}{\partial v}$$
- The partials are the basis for 1-vectors in the domain's space

We can apply $df$ on the vector field and get the transformed vectors as: $$df(X) = a \left( \frac{{\partial f}}{\partial u} \right) + b \left( \frac{{\partial f}}{\partial v} \right)$$ using our standard approach of applying 1-forms on vectors. Note that this operation will produce a vector in $\mathbb{R}^3$

In standard vector calculus, this operation is represented using jacobiam matrices, where the jacobian matrix is defined as the matrix of all elements in the output vector with respect to every element in the input vector (all coordinate directions).

The differential is the same as the jacobian in its effect, as: $$df(X) = J_{f}X$$ but this law does not generalize to infinite dimensions.

**Immersed surface** is defined as a map $f:U\to \mathbb{R}^n$ with the differential $df$ that is nondegenerate. This also means a mapping where non-zero vectors does not get mapped into zero vectors. $$df(X)|_{p} = 0 \iff X|_{p} = 0\quad \forall p \in U$$ It also means no region of the surface get "pinched" / "squashed"

**Note that, as long as surface is immersed, quantities like tangents, normals are well-defined, even if the map is not technically an embedding and self-intersections exists.**

Any immersion is locally an embedding (the reverse is also true).

![[Screenshot from 2023-04-16 16-12-24.png]]

- The example above is locally immersion though for points not at line $v=0$ and $v=\pi$

## Regular Homotopy

Regular homotopy is the nortion of a nice motion,, where there are no pinches, sharp creases, or stops. 

If we have 2 mappings on the same domain $f_{0}, f_{1} : U\to \mathbb{R}^n$, then the regular homotopian is the continously changing mapping between the given mappings, where $$h: U \times [0,1] \to \mathbb{R}^3, h(x,0) = f_{0}(x), h(x,1) = f_{1}(x)$$
- It is a mapping over space and time, in which for any infinitely small timesteps this mapping is a immersion.

For curves in 2D, the turning number determins the regular homotopy class. (For example, we cannot turn a circle inside-out wile remaining immersion at every time step)

## Riemannian Metric

The Riemannian Metric made use of the fact that properties of manifolds can be expressed using the measurements of lengths and angles of tangent vectors. 

![[Screenshot from 2023-04-16 16-33-16.png]]

Remanian metric is the encoding of these information, as $g(X, Y)$ for the above point $p$. 

**The Remannian metric is the smoothly-varying positive-definite bilinear form**. This metric is not for distance like common metrics, as: $$g : T_{p}\times T_{p} \to \mathbb{R}$$
- Where $T_{p}$ is the tangent space at point p.

A bilinear map is a function that takes two tangent vectors at a point on the surface and returns a scalar value. The map is linear with respect to each argument separately, hence the name "bilinear".

For an immersion $f : U\to \mathbb{R}^3$, Remannian metric is the measore of inner products for the mapped vectors for the origional vectors $(X,Y)$ around the same point on the domain. It is an induced matric where: $$g(X,Y) := \langle df(X),df(Y) \rangle $$
- This is the measure of all stretchings happened in the mapping process.

This induced metric also have an matrix representation, where: $$g(X,Y) = X^T I Y, I_{ij}= g\left( \frac{\partial}{\partial x_{i}} , \frac{\partial}{\partial x_{j}}\right) = \left\langle  df\left( \frac{\partial}{\partial x_{i}} \right), df\left( \frac{\partial}{\partial x_{j}} \right)  \right\rangle $$
- $x_{i},x_{j}$ are the 2 basis of the origional domain

And this can be also represented using jacobians, where: $$g(X,Y) = \langle df(X), df(Y) \rangle = (J_{f}X)^T (J_{f}Y) $$
Where we have the conclusion: $$I = J_{f} ^T J_{f}$$
Note that since the Remannian metric is an induced matric depending on the tangent space at point $p$, changing the point will cause changes to all the matrices defined above. 

The matrix $I$ is a 2 by 2 matrix that is always symmetric due to the symmetric of inner products. 

## Conformal Coordinates

Conformal coordinates are technically the similar concept as "arc-length parameterization" for curves. 

**The conformal parameterization $f$ is that for each point the induced metric si simply a positive rescaling of the 2D Euclidean metric, whereas all the angles on the domain are preserved into the surface.**  

Mathematically speaking, we have: $$g_{p}(X,Y)  = \phi_{p} \langle X,Y \rangle , \phi_{p} \in \mathbb{R}$$![[Screenshot from 2023-04-16 17-04-30.png]]

This conformal mapping is coordinate independent from the domain.

## Abstract Riemannian Metric

The abstract Riemannian Metric is the metric independent from the surface / mapping it is induced from and how it sits in its target space. It just define a smoothly-varyiong inner product at every point, given 2 vectors and point on the domain. 

For example, for a open disk in 2D space $U:= \{ p\in\mathbb{R}^2:\lvert p \rvert <1\}$, the **hyperbolic metric** is defined as the following scaled inner product: $$g_{p}(X,Y) = \frac{1}{(1-\lvert p \rvert ^2)^2}\langle X,Y \rangle $$
And in fact, the embedding for this mapping does not even exist in $\mathbb{R}^3$, but the outcomes of applying vectors onto this matrix can be calculated, together with other quantities like area, angle and even line integrals.

![[Screenshot from 2023-04-16 19-38-09.png]]

**Nash embedding theorem says given arbitrary Riemannian metric, there always be some global $C^k$ embedding in some sufficiently high-dimensional space that corresponds to the metric** 

This means that every Riemannian metric corresponds to some piece of geometry.

![[Screenshot from 2023-04-16 19-52-22.png]]

We can also describe a piece of geometry using the union of multiple mappings covering different domains, these overlapping submodules of the geometry is called charts. Each of these charts defines their own induced Riemannian metric.

Although local charts represent different mappings, the induced metrics woudl give identical measurements by definition. For a set of charts: $$\phi_{i} : \mathbb{R}^2 \supset U_{i} \to \mathbb{R}^n$$
We have: $$g_{i}(X,Y) = \langle  d\phi_{i}(X), d\phi_{i} (Y) \rangle$$
For a point $p$ on the intersection of 2 charts,  we can define a inter-chart mapping as $$\phi_{ij} = (\phi_{j}^{-1} \circ \phi_{i}) $$
Because of the metric inter-compatablity in defintion, for vectors on $U_{i}$, we transform it to the surface, and then apply the inverse mapping of $\phi_{j}$ to convert these vectors to $U_{j}$. Which means: $$g_{j}(d\phi_{ij}(X),d\phi_{ij}(Y)) = g_{i}(X,Y)$$
## Gauss Map

A vector is **normal** to a surface if it is orthogonal to all tangent vectors, where: $$\forall X, \langle N, df(X) \rangle = 0$$ Note that the normal is not unique for the surface at a given point. it is the orthogonal complement to the plane spanned by the tangent vectors.

**The Gauss map is a continuous map taking each point on the surface to a unit normal vector.**

There exists some surfaces that does not have a well-defined gauss map globally. 

![[Screenshot from 2023-04-16 20-25-17.png]]

For example, the Mobius band, the normal get inversed after traversing a cycle around the surface.

For any arbitrary embedded smooth closed surface, we can find a unit normal for the point (proved using the Hilbert proof). This also means the **gauss map is surjectiv**e.

However, this map is not injective, there can exist 2 points on the surface that have the same normal. Only when the shapes are strictly convex (there exists no place with flat surfaces) the gauss map is injective.

Given a patch of surface, we can compute an average normal using an integral, as: $$\frac{1}{area(\Omega)} \int _{\Omega} N \, dA $$
- Where $N\,dA$ is called the **vector area**, or a vector-valued 2-form. It is not just the differential "area" 
- We can express this using exterior calculus, as: $$df \land df(X,Y) = df(X) \times df(Y) - df(Y)\times df(X) = 2 df(X)\times df(Y)$$
- Because the 2-forms are vector valued, they are not necessarily zero
- Note that since $df(X)$ and $df(Y)$ are already tangent to the surface, their cross product would yield the normal of the surface, with the magnitude equal to 2 times the area of the little parallelgram spanned by the vectors.

Using the properties above, we can write: $$df \land df(X,Y) =2 df(X)\times df(Y) = 2NdA(X,Y)$$ and we can define the "area vector" as $$\mathcal{A} = \frac{1}{2}df \land df$$ if we integrate the normal over the surface, it is the same as $$2\int _{\Omega} N\, dA = \int _{\Omega} df \land df $$
Using the fundamental rule of wedge product, we can rewrite: $$df \land df = d(f df) - f(ddf) =d(fdf) \implies \int _{\Omega} d(fdf) \,  $$
- Note this works becaus $f(ddf) =0$ and the product of 1-forms $df$ is represented using the wedge product

Here, we can use the stock's theorem (general), and in 3 dimensions, we woule have: $$\int _{\partial\Omega} fdf  = \int _{\partial \Omega} f(s) \times df(T(s)) ds$$
- This means, in order to know the "total normal" of a surface patch, **we can walk on the arc-length parameterized boundary of the curve, and integrating the cross product of the position and the tangent of the boundary.** (This quantity is positional invariant)

This also means, for arbitrary smooth surface patches . its total normal will be same if they have the same boundary.

This also means that the total normal of a closed surface is always zero.

## Immersed surfaces with Exterior Calculus

Note that the wedge product and exterior derivatives are geometry independent, while the hodge star is strictly geometry dependent.

The **induced Area 2-Form** is the way of obtaining the signed area created by 2 vectors stretched in the transformation. In 3 dimensions, we gace: $$df \land df(X,Y) = 2 df(X)\times df(Y)$$ and we have said earlier, as $$df \land df (X,Y) = 2NdA(X,Y)$$
- Here $dA$ is the area 2-form we are looking for, hence$$dA = \frac{1}{2} \langle N,df \land df \rangle $$
- This inner product works because $N \cdot N=1$

The **induced Hodge star** for a 0-form $\phi$ is defined as: $$\star\phi = \phi dA$$![[Screenshot from 2023-04-17 15-28-02.png]]

And suppose $\omega$ is a 2-form on $f(U)$, then its Hodge star dual 0-form $\phi$ such that $\omega  = \phi dA$

The **Complex Structure** on a surface discribes how 90 degree rotation works for vectors. 

For example, in $\mathbb{R}^2$ the rotation is done with $(x,y)\to(-y,x)$, as: $$\mathcal{J}_{R^2} :=\begin{bmatrix}
0&-1 \\
1&0
\end{bmatrix}, \mathcal{J}_{R}\begin{bmatrix}
x \\
y
\end{bmatrix} = \begin{bmatrix}
-y \\
x
\end{bmatrix}$$
For a surface immersed in $\mathbb{R}^3$, the 90 degree rotation can be defined with a cross product against the unit normal $N$ (making the output orthogonal to both vectors),  as: $$df(\mathcal{J}_{f}X) := N\times df(X)$$
- Note that $J_{f}$ is induced through the immersion $f$

And $J_{f}X$ is the vector in the domain $U$ in which its image satisfies the orthogonal relationship above. (They are not necessarily 90 degrees apart in the domain). A immersion is conformal if and only if $J_{f} = J_{\mathbb{R}^2}$

![[Screenshot from 2023-04-17 15-44-36.png]]

On the standard 2d euclidian surface, the hodge star of a 1-form is the counter clockwise 90 degree rotation of the vector. Using our definition above, we have: $$\star_{\mathbb{R}^2}\alpha(X) = \alpha(\mathcal J _{\mathbb{R}^2}X)$$
An in some curved surface, the hodge star will be: $$\star_{f}\alpha(X) = \alpha(\mathcal J _{f}X)$$
Note: **The Riemannian metric on a surface can be decomposed into an area form and complex structure**
$$g(X,Y) = dA(X,JY)$$
- This is basically saying, that the riemannian metric (warped dot product) betweem 2 vectors is the same as measuring the area of the vector cross the 90 degree rotation of the other vector.
- This is the extension of the rule in 2d plane where, $X \cdot Y = X \times (JY)$ (Note that is cross product is the special definition where $x\times y = x_{1}y_{2}-x_{2}y_{1}$)

The sharp and flat on a surface is defined differently from the flat space. as: $$X^\flat (Y) := g(X,Y)\quad g(\alpha ^\sharp, Y) := \alpha(Y)$$
![[Screenshot from 2023-04-17 16-13-22.png]]

