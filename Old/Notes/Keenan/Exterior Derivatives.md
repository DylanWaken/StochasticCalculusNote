
----
The divergence is defined as the gradient field of a function dot product with another vector field $X$, in which we have: $$\nabla  \cdot X = \frac{\partial}{\partial x^1} X^1 +\dots+ \frac{\partial}{\partial x^n} X^n$$
intuitively speaking, the divergence measures the alignment between the vector field and gradient vectors of the vector field at the specific location. 

In practice, the divergence gives the level of the vectors converging or diverging at a specific position. 

The curl is another critical value that is defined by:
$$\nabla  \times X$$
Because of the properties of cross product, we only have curl defined in 3 dimensional space, as:
$$\nabla \times X = \left( \frac{{\partial}}{\partial x^2}X^3 -\frac{\partial}{\partial x^3}X^2, \frac{\partial}{\partial x^3} X^1 -\frac{\partial}{\partial x^1}X^3, \frac{\partial}{\partial x^2} X^1 -\frac{\partial}{\partial x^1}X^2\right)$$
Curl measures how much a vector field "spins" around a particular location, as shown below 

![[Screenshot from 2023-03-23 14-10-19.png]]

(above is the visualized version of vector fields with high divergence and high curl)

## Main Properties

Exterior derivatives is a unique linear map $d:\Omega_{k} \to \Omega_{k+1}$ has 3 critical properties (for real valued function $\phi$ and vector field $X$ of same dimension):

- Differential :  for $k=0$, $d\phi(X) = D_{X}(\phi)$ (the directional derivative of $\phi$ on the directions of vectors in the field $X$)
- Product Rule :  $d(\alpha \land \beta) = d\alpha \land \beta + (-1)^k \alpha \land d\beta$
- Exactness :  $d \circ d = 0$ 

A **Differential** is a unique k-form that by applying it to k-vectors it will give the rate of change in the vector's direction. It is independent from inner product and positions of the forms.

The **Product rule** can be considered for a k-form $\alpha$, l-form $\beta$, we have: $$d(\alpha \land \beta) = d\alpha \land \beta + (-1)^k \alpha \land d\beta$$
This rule can be understood as, since $\alpha \land \beta$ gives a (k+l)-form, the change in the wedged form is the total change of the first k-form introduced to the current (k+l)-form, and the total change of the second l-form introduced to the current (k+l)-form, like the product rule between functions in traditional calculus.

![[Screenshot from 2023-03-27 16-28-40.png]]

The $(-1)^k$ term is used to cancel out the antisymmetry of swapping orders of wedge product. 

The **Exactness** rule stands for the differential of differential is always zero. (The analogy to the "curl of the gradient" to be zero. )

## Exterior derivatives

The discussion starts with the derivative of the 0-form.

For a real-valued function $\phi : \mathbb{R}^n \to \mathbb{R}$. the exterior differential is defined as:
$$d\phi = \frac{{\partial \phi}}{\partial x^1}dx^1 + \dots + \frac{{\partial \phi}}{\partial x^n}dx^n$$
- Note that $dx^i$ is the orthnormal basis of $\mathbb{R}^n$ , and the partials are just the relative rate in change between $\phi$ and $x^i$

A  interesting relationship arised from this definition. As $\nabla \phi$, or the gradients of the function, is a vector field with extremely similar look. In fact, we can derive the following relationship, that:
$$\nabla \phi = (d\phi)^\sharp$$
- The differential is the 1-Form of the gradient vectors.


The directional derivatives can also be defined upon the exterior differential, as the directional derivative is the dot product between the directional unit vector and the gradient vector, as: $$d\phi(u) = \frac{{\partial \phi}}{\partial x^1} u^1 + \dots + \frac{{\partial \phi}}{\partial x^n} u^n$$
Where we easily find the following expression:
$$d\phi(u) = u \cdot \nabla \phi$$
#### Properties:

Since the derivative operation is linear (a infinitely small difference), we consider the differential to be linear.  In the classic calculus, the product rule is defined as:
$$\frac{\partial}{\partial x} (f(x),g(x)) = f'(x)g(x) + f(x) g'(x)$$
Since the k-forms is a measure of the signed volume, the same intuition also works for the exterior derivatives when 2 k-forms are wedged together, as: 
$$d(\alpha \land \beta) = d\alpha \land \beta + (-1)^k \alpha \land d\beta$$
which says that the rate of change of the overall volume can be expressed in terms of changes in the constituent volumes.

## Exterior Derivative of 1-Forms

Assume that $\alpha$ is a 1-form in the $\mathbb{R}^3$ space, with the linearity of the differentials we can write its rate of change as:
$$d\alpha = d(\alpha_{1}dx^1 + \alpha_{2}dx^2 + \alpha_3{dx^3}) = d(\alpha_{1}dx^1) + d(\alpha_{2}dx^2) + d(\alpha_{3}dx^3)$$
If we consider every multiplication to be the wedge product between the 0-form $\alpha_{i}$ and the corresponding basis 1-form $dx^i$, we have the following relationship: $$d(\alpha_{j}\land dx^j) = (d\alpha_{j}) \land dx^j + \alpha_{j} \land (d(dx^j)) = \sum_{i}\frac{{\partial \alpha_{j}}}{\partial x^i} dx^i \land dx^j$$
- The second term $\alpha_{j} \land (d(dx^j))$ evaluates to 0
- The first term can be expanded using the 0-form differentials we defined above

If we list out the entire expression, we would have: $$d \alpha = \begin{matrix}
\frac{{\partial \alpha_{1}}}{\partial x^1} dx^1 \land dx^1 &+&\frac{{\partial \alpha_{1}}}{\partial x^2} dx^2 \land dx^1&+&\frac{{\partial \alpha_{1}}}{\partial x^3} dx^3 \land dx^1 \\
\frac{{\partial \alpha_{2}}}{\partial x^1} dx^1 \land dx^2 &+&\frac{{\partial \alpha_{2}}}{\partial x^2} dx^2 \land dx^2&+&\frac{{\partial \alpha_{2}}}{\partial x^3} dx^3 \land dx^2 \\ 
\frac{{\partial \alpha_{3}}}{\partial x^1} dx^1 \land dx^3 &+&\frac{{\partial \alpha_{3}}}{\partial x^2} dx^2 \land dx^3&+&\frac{{\partial \alpha_{3}}}{\partial x^3} dx^3 \land dx^3 \\
\end{matrix}$$
By removing all the zero terms and combine repeating terms using the antisymmetry, we have: $$
d \alpha = \left( \frac{{\partial \alpha_{3}}}{\partial x^2} - \frac{{\partial \alpha_{2}}}{\partial x^3}\right)dx^3 \land dx^2 + \left( \frac{{\partial \alpha_{3}}}{\partial x^1} - \frac{{\partial \alpha_{1}}}{\partial x^3}\right)dx^3 \land dx^1 + \left( \frac{{\partial \alpha_{2}}}{\partial x^1} - \frac{{\partial \alpha_{1}}}{\partial x^2}\right)dx^2 \land dx^1
$$
Note that the output of this operation gives as a 2-form based on the 2-form basis

**Generally speaking, the derivative of a n-form would yield a (n+1)-form** 

In the three dimensional case, this is exactly as the curl of the vector field. In reality, the value of $d\alpha$ is similar to the definition for the curl of the vector field. Through few steps on arbitrary vector field $X$, we would have the conclusion that:
$$\nabla \times X = (\star dX^\flat)^\sharp$$

- $\flat$ operation convers the vector field into a 1-form $X^\flat$
- the computation of $d$ would give a output looks like curl but expressed in 2-form $dX^\flat$
- The hudge star converts the 2-form into its 1-form orthogonal complement
- The final $\sharp$ operation recovers the 1-form back to the vector field.

The divergence can also be represented through exterior derivative. In the 2 dimensional senarial, the divergence can be described through the 90 degree rotation on the vectors in the vector field and compute the curl. In our exterior algebra, we have: $$\nabla  \cdot X = \star d \star X^\flat$$
- Note this operation works because hudge star of 1-vectors in 2d space woule be the counterclockwise 90 degree rotation of the vector.

By applying this operation to the higher dimensions, we woudl have:
$$\begin{align}
\star X^\flat &= \star(X_{1}dx^1 + X_{2}dx^2 +X_{3}dx^3) \\
&= X_{1}dx^2 \land dx^3 + X_{2} dx^3 \land dx^1 + X_{3} dx^1 \land dx^2 \\
d \star X^\flat &= \frac{{\partial X_{1}}}{\partial x^1} dx^1 \land dx^2 \land dx^3\\
&+ \frac{{\partial X_{2}}}{\partial x^2} dx^2 \land dx^3 \land dx^1 \\
&+ \frac{{\partial X_{3}}}{\partial x^3} dx^3 \land dx^1 \land dx^2
\end{align}$$
And by simplify this equation we have:
$$d \star X^\flat = \left( \frac{{\partial X_{1}}}{\partial x^1} + \frac{{\partial X_{2}}}{\partial x^2} + \frac{{\partial X_{3}}}{\partial x^3} \right) dx^1 \land dx^2 \land dx^3$$
And finally applying the hodge star on the equation would give us the divergence:
$$\star d \star X^\flat = \frac{{\partial X_{1}}}{\partial x^1} + \frac{{\partial X_{2}}}{\partial x^2} + \frac{{\partial X_{3}}}{\partial x^3} $$
Therefore,for any scalar field $\phi$ and vector field $X$ we have:
$$\begin{align}
\nabla \phi &= (d\phi)^\sharp \\
\nabla \times X &= (\star dX^{\flat})^\sharp \\
\nabla \cdot X &= \star d \star X^{\flat} 
\end{align}$$

Operation relationships:

2-Dimensional space:

![[Screenshot from 2023-03-27 17-11-35.png]]

3-dimensional spaces:

![[Screenshot from 2023-03-27 17-12-53.png]]