----
![[Screenshot from 2023-03-23 19-57-17.png]]

In the traditional calculus, the way to find the area of an arbitrarily bounded region is to sum up all the infinitely small sub-squares of the region, as:
$$A_{\Omega} = \sum_{i}A_{i}$$
When the size of the squares approaches zero, our relationship became:
$$A_{\Omega} = \int _{\Omega} dA $$
To integrate over a real-valued function $\phi : \Omega \to R$, we have the following weighted sum:
$$\sum_{i} A_{i} \phi (p_{i}) = \int _{\Omega} \phi \, dA $$
- $p_{i}$ is the center of each little piece of area evaluated by function $\phi$
- This integral is like the weighted sum of area

If we assign a differential 2-form $\omega$ to the region $\Omega$, we would have the integal over the little areas that applied to the 2-forms as:
$$\sum_{i} \omega_{p_{i}}(u_{i},v_{i}) = \int _{\Omega} \omega $$
![[Screenshot from 2023-03-27 17-48-33.png]]

- This give the area measured by the differential form
- On the 2-form for $\omega := f(x,y)dx\land dy$ over the plane $\Omega$, it is equivalent of evaluating a double integral over $dx$ and $dy$ (when it is possible to do so): $$\int _{\Omega} \omega  = \int f(x,y) \, dx \land dy$$
A different intution can be when integrating over a curve $\gamma$ in a dbove also means thatifferential 1-form $\alpha$ in $\mathbb{R}^2$, we have the following relationship: $$\int _{\gamma} \alpha \approx \sum_{i} \alpha_{p_{i}}(t_{i})\quad \int _{\gamma} \star \alpha\, \approx\sum _{i} \star\alpha_{p_{i}}(t_{i}) =\sum_{i} \alpha_{p_{i}}(t_{i})$$
- Which measures the alignment between the curve direction ($t_{i}$) and differential one form and sum it.
- The hudge star gives the flux of the 1-form through the curve.

**The boundary of a set is defined as the place where points can not preserve an infinitely small k-dimensional ball around it such that every point in that ball is also within the set**

We normally label the boundary of set $\Omega$ by the label $\partial \Omega$

The boundary of the boundary is always the empty set

## Stoke's theorem

The stoke's theorem in exterior calculus is: $$\int _{\Omega} \, d\alpha  = \int _{\partial \Omega} \alpha $$
- This is the same as the fundamental theorem of calculus, as the change in the boarders is the total change within the region. 

For example, we have the **divergence theorem**, saying: $$\int _{\Omega} \nabla \cdot X\, dA = \int _{\partial \Omega} n\cdot X \, dl $$
- $l$ is the little piece of the boarder, $A$ is the little piece in the region

![[Screenshot from 2023-03-27 18-21-05.png]]

**What goes in must come out:** the flow on the boarder is the total divergence within the region. 

The theorem connects to stock's theorem as: $$\int _{\Omega} \, d\star\alpha = \int _{\partial \Omega} \, \star \alpha $$
- This hudge star representation on LHS is expression for divergence we derived earlier in [[Exterior Derivatives]]
- Note that the hudge star in 2 dimensions would rotate the 1-forms counter clockwise, which means the RHS of the equation above as the application of 1-form $\alpha$ onto the normal vectors of the boundry 

If we use the **Green's theorem** in the vector calculus, it is equivalent of saying: $$\int _{\Omega} \nabla \times X \, dA = \int _{\Omega} t \cdot X\, dl  $$
This is the "**what goes around come around**", as the tangent alignment with the vector field on the boarder is the total curl within the region

![[Screenshot from 2023-03-27 18-21-05.png]]

And by substituting the definition of curl in exterior algebra, we have:
$$\int _{\Omega} \, d\alpha = \int _{\partial \Omega} \, \alpha $$
