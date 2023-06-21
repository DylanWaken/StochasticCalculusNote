----
## Discrete Exterior Derivatives

Exterior derivatives are unique lilnear maps from differential k-forms to differential (k+1) forms

it satisfies the product rule:
$$d(\alpha\land \beta) = d\alpha \land \beta +(-1)^k \alpha \land d\beta$$
- where $k$ is the degree of $\beta$

it yields zero if we apply it twice (curl of gradient):
$$d \circ d = 0$$
In the discrete case, taking the drivative of a 0-form would give us a differential 1-form. If we only know the original 0-form on the vertices, we can still compute the differential 1-form from the derivative, In which we will try to integrate over edges of meshes.

Assume we have vertices $v_{0}$ and $v_1$ connected by directed edge $e$, we jave:

- $\hat{\phi}$ as the discrete 0-form only evaluated on vertices
- $\hat{d\phi}$ as the discrete 1-form, or the discrete exterior derivative we are looking for

We have the following definition, using the general stock's theorem:
$$(\hat{d\phi})_{e} = \int _{e} \, d\phi = \int _{\partial e} \, \phi = \phi_{v_2} - \phi_{v_{1}}$$
- We evaluate the function at the two vertices

For a 2-simplex $\sigma$ (or a triangle), we can assign the discrete differential 1-form to all the directed edges $e_{1},e_{2},e_{3}$,  and we will be able to use the stoke's theorem again:
$$(\hat{d\alpha})_{\sigma} = \int _{\sigma} \, d\alpha = \int _{\partial \sigma} \, \alpha  = \sum_{i=1}^3 \int _{e_{i}} \, \alpha = \sum_{i=1}^3 \hat{\alpha}_{i}$$
- The final integral is exactly how we defined discrete 1-forms

ln general, the discrete exterior derivative is the same as **the co-boundary operator for co-chains** (I didn't get it for now, understand in the future after learning more topology)

Note, the discrete exterior derivative have no dependency on the actual spacial structure of the mesh, as long as the vertices have identical values as discrete differential 0-form

The discrete exterior derivative is a lienar map from values on the k-simplices to values on (k+1)-simplices. It can be defined as a recusrive relationship from 0-simplices to n-simplices. 

![[Screenshot from 2023-04-07 15-15-32.png]]
- The matrix representation of DED
![[Screenshot from 2023-04-07 15-17-12.png]]
The non-zero entries inthe matrices stands for the relative orientations of the adjacent (k-1)-simplices for the target k-simplex

**Taking the smooth exterior derivative and then discretizing yields the same result as discretizing and then applying the discrete exterior derivative**

Note, taking the discrete exterior derivative on a DED output would yield zero, as the coboundary of coboundary is always zero.

## Dual Discrete Differential Form

Poincare Duality: in a n dimensional space, every k-simplx can be assigned with a dual simplex with (n-k) dimensions. 

The dual k-form is the value per dual cell.

![[Screenshot from 2023-04-07 15-29-39.png]]

Note that the primal and dual forms does not exist in smooth settings, since you do not have the mesh made of k-simplices where you can define dual simplices on.

The rules for computing these dual derivatives is the same as primal derivatives

## Discrete Hodge Star

- The exterior derivative is only relevant to the connectivity of the mesh
- But the hodge star is geometry related

The **circumcenter** is the center of the smallest k-sphere that pass through all vertices of a k-simplex.

- For a 2-simplex: triangle circumcenter
- For a 1-simplex: edge midpoint
- For a 0-simplex: vertex itself

**All primal and dual cells would meet orthogonally.**

Note that it is possible to get negative signed lengths/areas/volumes as dual cells

The discrete hodge star can be considered for a k-simplex $\sigma$ and a dual (n-k)-cell $\sigma*$. If $\alpha$ is a constant differential form, then we will see the relationship due to the orthogonal properties.:
$$\frac{\star\hat{\alpha}}{\hat{\alpha}} = \frac{|\sigma*|}{|\sigma|}$$
- This ratio works because we are integrating an k-simplex over a differential k-form, and integrating the orthogonal complement of the k-simplex over the hodge star of the differential k-form. Therefore, the only difference between these 2 integrals will be the ratio of volumes (since they fundamentally represented the same thing)

For an example in the 3d space: 

![[Screenshot from 2023-04-07 17-42-58.png]]

If we apply the formula we have, we will get the conclusion that:
$$\hat{\star w_{ab}} = \frac{l_{ab}}{A_{ijk}} \hat{w_{ijk}}$$
This difinition is called the **diagonal hodge star.** This name came from the fact that the constant scaling on the RHS is normally done through the multiplication with a diagonal matrix:$$\star_{k} = \begin{bmatrix}
\frac{|\sigma_{1}^\star|}{|\sigma_{1}|}&\dots&0 \\
&\dots& \\
0&\dots&\frac{|\sigma_{n}^\star|}{|\sigma_{n}|}
\end{bmatrix} \in \mathbb{R}^{n\times n}$$ Note: this is just an estimate, its not an actual accurate value.

Computation details:

![[Screenshot from 2023-04-07 17-55-26.png]]