----
A Polyhedron is the geometric object that is formed by the closed surface defined through combining n-polygoons through edges. 

If $X$ is a polyhedron, we define

- $E$ the set of edges in $X$ (1-simplex)
- $F$ the set of faces in $X$
- $V$ the set of vertices in $X$

The Eular's theorem says, for some polyhedron, the following relationship always satisfies: $$|V| - |E |+ |F| = 2$$
The condition of target polyhedron is that there exists a continuous transformation that turns the polyhedron into a spherical surface. This is the **Topological Property** of the polyhedron

For polyhedrons that can be continuously transformed into a donut shape (Torus with $g=1$), the eular's therom changes to the following relationship: $$|V| - |E| + |F| = 0$$
Now, if we assume that the polyhedron that can ransformed continuously into a closed smooth shape of $n$ holes (or $g=n$), then the eular's theorem became: $$|V| - |E| + |F| = 2-2g$$
- Here: $g$ is the **Genus** of the shape

For any polyhedrons, the outcome of eular theorem is only dependent on the genus of the closed smooth surface of the polyhedron's surface can be transformed into, and is independent from the exact shape of the polyhedron.

The Eular characteristic is a topological invariant

## Closed form and exact forms

Example: assume $\Omega \subset \mathbb{R}^2$ , and $\omega$ as a differential 1-form ([[1-Forms and vectors]]) defined as:
$$\omega = P(x,y)dx + Q(x,y)dy$$
Then the differential of this 1-form is in the 2-form given as:
$$d \omega  = dP \land dx + dQ \land dy$$
Using the standard expansion of the wedge product we have:
$$d \omega = \left( \frac{{\partial P}}{\partial x}dx + \frac{{\partial P}}{\partial y}dy \right) \land dx + \left( \frac{{\partial Q}}{\partial x}dx + \frac{{\partial Q}}{\partial y}dy \right) \land dy$$
Through cancel out the zero terms, we have: 
$$d \omega = -\frac{{\partial P}}{\partial y} dx \land dy + \frac{{\partial Q}}{\partial y} dx \land dy = \left( \frac{{\partial Q}}{\partial y} - \frac{{\partial P}}{\partial x} \right) dx \land dy$$
Now, if we have $d \omega  =0$, then we have $\omega$ as the closed 1-form on $\Omega$

Let $f: \Omega \to \mathbb{R}$ be a smooth function int he domain $\Omega$, we define the differential : $$df := \frac{{\partial f}}{\partial x} dx + \frac{{\partial f}}{\partial y}dy$$
if $\omega$ is a differential 1-form on the domain $\Omega$, then $\omega$ is a **exact form** if and only if:
$$\omega = df : f \in C^{\infty}$$
Note that any exact forms must be closed forms, as:
$$\begin{align}
\omega = df\implies d\omega &= d\left( \frac{{\partial f}}{\partial x} dx + \frac{{\partial f}}{\partial y}dy \right) \\
&= \left( \frac{{\partial ^2 f}}{\partial x\partial y} - \frac{{\partial ^2 f}}{\partial y\partial f} \right) dx \land dy \\
&= 0
\end{align}$$
Note: if $\omega$ is Simply connected space, then any closed form must be exact forms. otherwise this conclusion is unecessarily true.

