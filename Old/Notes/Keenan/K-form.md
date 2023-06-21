----
K-form is the extension of the one form define in [[1-Forms and vectors]]

In the original 1-from definition, the thing is defined as a measure of the "projected volume" of a vector onto a coordinate axis. Similarly, the k-form would be the projected volume of a k-vector onto a k-dimensional axis. 

For example, the projection of a plane in 3 dimensional space would be the area of the "shadow" it casts onto a plane formed by a 2-form on the normal direction, as:

![[Screenshot from 2023-03-23 11-33-41.png]]

If we consider the plane made up of orthnormal 1-forms $\alpha$ and $\beta$, then the projected vectors defining the k-vector would have the following components: $$\begin{align}
&u' = (\alpha(u), \beta(u))^T, \\
&v' = (\alpha(v), \beta(v))^T
\end{align}$$
And therefore the area of the projected k-vector can be computed as:
$$u'\times v' = \alpha(u)\beta(v)-\alpha(v)\beta(u)$$
With [[Wedge Product]], we can define the same concept as:
$$\alpha\land \beta (u,v) = \alpha(u)\beta(v)-\alpha(v)\beta(u)$$
Note that this is also the same asFor a k-vector $\alpha$, l-vector $\beta$ and m-vector $\gamma$, we have

- Antisymmetry: $\alpha \land \beta = (-1)^{kl} \beta \land \alpha$
- Associativity: $\alpha \land (\beta \land \gamma) = (\alpha \land \beta)\land \gamma$

In the special case where $\beta$ and $\gamma$ have the same degree, we have

- Distributivity: $\alpha \land (\beta+\gamma) = \alpha \land \beta + \alpha \land \gamma$

 the determinant:
$$\alpha\land \beta (u,v) = \det ( \begin{bmatrix}
\alpha(u)&\alpha(v) \\
\beta(u)&\beta(v) 
\end{bmatrix})$$

If we considered the projection over 2 different planes spanned by $\alpha ,\beta$ and $\alpha,\gamma$, the total projection area is the: $$\begin{align}
\alpha \land \beta (u,v) + \alpha \land \gamma(u,v) &= \alpha(u)(\beta(v) +\gamma(v)) - \alpha(u)(\beta(u)+\gamma(u)) \\
&= (\alpha \land (\beta+\gamma))(u,v)
\end{align}$$
This property proved the distribution property of wedge product: $$\alpha \land (\beta + \gamma) = \alpha \land \beta + \alpha \land \gamma$$
This projection operation is actually what defined the idea of wedge products.

For the projection of a 3-vector, we can apply the same technique and write it as the determinant: $$
\alpha \land \beta \land \gamma(u,v,w) = \det(\begin{bmatrix}
u'&v'&w'
\end{bmatrix}) = \det\left(\begin{bmatrix}
\alpha(u)&\alpha(v)&\alpha(w) \\
\beta(u)&\beta(v)&\beta(w)  \\
\gamma(u)&\gamma(v)&\gamma(w)
\end{bmatrix}\right)
$$
Since the volume does not change by the face we choose, as we have:
$$\begin{align}
\alpha \land \beta \land \gamma(u,v,w) &= (u'\times v') \cdot w' \\
&= (v'\times w') \cdot u' \\
&= (w'\times u') \cdot v'
\end{align}$$
![[Screenshot from 2023-03-23 11-56-26.png]]

And this proves the associativeness of the wedge product:
$$(\alpha \land \beta)\land \gamma = \alpha \land(\beta \land \gamma)$$
Note: the determinant definition of the wedge product also gives the reason for its antisymmetry, as:
$$\alpha \land \beta = - \beta \land \alpha$$
For a k-form $\alpha$, l-form $\beta$ and m-form $\gamma$, we have

- Antisymmetry: $\alpha \land \beta = (-1)^{kl} \beta \land \alpha$
- Associativity: $\alpha \land (\beta \land \gamma) = (\alpha \land \beta)\land \gamma$

In the special case where $\beta$ and $\gamma$ have the same degree, we have

- Distributivity: $\alpha \land (\beta+\gamma) = \alpha \land \beta + \alpha \land \gamma$

In general, the antisymmetry property counts the number of swaps, like the swapping of columns in determinent computation