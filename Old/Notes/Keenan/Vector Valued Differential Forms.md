----
In the original definition, differential forms are design as linear maps from k-vectors to real numbers. However, geometry operates on vertices in multidimensional space. Therefore, we would need vector-valued k forms. 

For a $\mathbb{R}^n$-valued k-form on $\mathbb{R}^m$, the mapping is between the wedged vectors and the target space, as:
$$\{v_{1},\dots,v_{k}\}\in \mathbb{R}^m \to \mathbb{R}^n$$
Where $v_{1},\dots,v_{k}$ is the set of vectors that are wedged together to form the target k-vector.

This operation is fully anti-symmetric (meaning changing odd order to the vectors would negate the output). 

This mapping is linear, for example, we can define a $\mathbb{R}^3$-valued 1-form as: $$\alpha:\mathbb{R}^2 \times \mathbb{R}^2 \to \mathbb{R}^3\quad \alpha(u,v)=-\alpha(v,y)$$
Is linear as: $$\alpha(au+bv,w)=a\alpha(u,w)+b\alpha(v,w)\quad \forall u,v,w \in \mathbb{R}^2,a\in \mathbb{R}$$

The example of such transformation is defined as: $$\alpha := v_{1}e^1+v_{2}e^2 ,v_{1},v_{2}\in \mathbb{R}^3$$
- Here $v_{1},v_{2}$ are vectors in $\mathbb{R}^3$, and $e^1$ and $e^2$ are the 1-form-basis in $\mathbb{R}^2$. When  we apply some 1-vector $u$ to this transformation, we will have: $$v_{1}e^1(u) +v_{2}e^2(u)$$ note that $e^1(u)$ and $e^2(u)$ would produce scalars.

## Wedge product

In the $\mathbb{R}^3$ space, we use the cross products between 3-valued k-forms, where if we have some k-vectors $$\alpha,\beta:V\to \mathbb{R}^3$$
We compute the wedged k form as: $$\alpha \land \beta (u,v) = \alpha(u)\times \beta(v) -\alpha(v) \times \beta(u)$$
Note that the rule of anti-symmetry will be different for 3-valued forms:
$$\alpha \land \beta (u,v)= - \alpha \land \beta(v,u)\quad \beta \land \alpha(u,v) = \alpha \land \beta(v,u)$$
as we have:

![[Screenshot from 2023-04-11 18-39-50.png]]

This is explained as the antisymmetry of cross product canceles out the antisymmetry in wedge product.

The self wedgeing in the R-3 valued are also non-zero, as $$\alpha \land \alpha(u,v)= \alpha(u) \times \alpha(v) -\alpha(v)\times \alpha(u) = 2\alpha(u)\times \alpha(v)\neq 0$$
## Exterior Derivatives

If we have an $\mathbb{R}^n$ valued k-form, the operations are aligned with real-valued k-forms. 

![[Screenshot from 2023-04-11 19-04-42.png]]

