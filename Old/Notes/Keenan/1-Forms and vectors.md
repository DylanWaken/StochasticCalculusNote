----
1-Form (or a covector) defines a function that maps a vector to a scalar, as: $$\alpha :\mathbb{R}^n\to \mathbb{R},\alpha(v) \in \mathbb{R}$$
In a euclidian space, $\alpha$ can be represented as a dot product between vectors: $$\alpha(v) = \alpha_{v}^Tv$$
Note: under other curved metrics this rule will not apply.

To understand this system, we define the orthnormal basis of a euclidian space to be:$$e_{1} = \frac{\partial}{\partial x^{1}},\dots,e_{n} = \frac{\partial}{\partial x^{n}}$$
And the basis of the 1-Forms corresponding to the basis vectors as:
$$dx^1,\dots, dx^n$$
This definition cames from the idea of [[Tangent space]]

Note: these are not standard differentials, they are just the representation of orthnortmal basis, where we can write every vector in the space as: $$v=v^1 \frac{\partial}{\partial x^1}+\dots+v^n \frac{\partial}{\partial x^n}, \quad\alpha=\alpha_{1}dx^1+\dots+\alpha_{n}dx^n$$
The basis has the following properties: $$dx^i \left( \frac{\partial}{\partial x^j} \right) = \delta^i_{j} = \begin{cases}
1, i=j \\
0,\text{otherwise}
\end{cases}$$
- This is true because since the basis vectors are orthnormal, the projection of a vector onto other basis vectors would only yield non-zero value if they are the same vector, since orthnormal vectors have zero dot products.

And by using this basis we can represent a arbitrary 1-form in the n dimensional space as:
$$\alpha(v) = \sum_{i} \alpha_{i}dx^i \left( \sum_{j} v^i \frac{\partial}{\partial x^j}\right) = \sum_{i}\alpha_{i}v^i$$
- This is analegy to the output of the dot products. 

There exists the **flat** and **sharp** transformations, as we can transform between 1-forms and vectors. In euclidian space, This is given as the function:
$$\alpha^\sharp \to v_{\alpha}, v^{\flat}\to \alpha_{v}$$
And this operation is defined as:
$$\begin{align}
&\alpha = \sum_{i}a_{i}dx^i \to \alpha^\sharp = \sum_{{i}}\alpha^i \frac{\partial}{\partial x^i} \\
&v = \sum_{{i}}v^i \frac{\partial}{\partial x^i} \to v^\flat = \sum_{i} v_{i}dx^i
\end{align}$$
The name came from the similar way sharp and flat works in music.

