----
In differential geometry, a tangent space is a mathematical concept that describes the set of all possible tangent vectors to a manifold at a given point.

Intuitively, a tangent vector at a point on a manifold can be thought of as an arrow that points in the direction of the curve that passes through that point. The set of all possible tangent vectors at a point is called the tangent space at that point.

For example, the tangent space of a 2 dimensional curve is a 1 dimensional space. Let $f:\mathbb{R}\to \mathbb{R}$, since, the tangent vector at each point is given by $<1,f'(x)>$, we have tangent space (span of tangent vectors) at a particular point $p : (x,y)$ as: $$T_p{f} = c\begin{bmatrix}
1 \\
\frac{df}{dx} 
\end{bmatrix} = c\begin{bmatrix}
dx \\
df
\end{bmatrix}, c\in \mathbb{R}$$
Now if we call the end dimension of this function $f$ as $y$, then our tangent space will be:
$$T_p{f}= c \begin{bmatrix}
dx \\
\frac{{\partial f}}{\partial x}dy
\end{bmatrix},c\in\mathbb{R}$$
Here $dx, dy$ is the basis of the tangent space at a specific point, its a special coordinate system for tangential vectors.

In the more general case, if we write the two dimensional curve as some relation:
$$C = \begin{bmatrix}
x(t) \\
y(t)
\end{bmatrix} \implies T_p{C} = c \begin{bmatrix}
x'(t)dx \\
y'(t) dy
\end{bmatrix},c\in\mathbb{R}$$
$dx,dy$ can be though of functions that maps from the tangent space to real values, as: $$
\begin{align}
&dx : T_{f} \to \mathbb{R} \\
&dy : T_{f} \to \mathbb{R}
\end{align}$$
- It is just the $x$ and $y$ components of tangent vectors

And in this case we have: $$dx (C) = cx'(t), dy(C) = cy'(t)$$



