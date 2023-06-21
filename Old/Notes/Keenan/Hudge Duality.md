----
![[Screenshot from 2023-03-23 11-33-41.png]]

In the projection of the previous chapter, we have [[K-form]] measuring the drea of the signed projected volume of a k-dimensional parallelepiped. 

**The Hudge Duality states the fact since the k-dimensional volume in an n-dimensional space can be specified either by k directions or by a complementary set of (n − k) directions.** (In this case, the projection of a 2-vector onto the 2-form can be represented as):
$$\gamma(u\times v) =\alpha \land \beta (u,v)$$
- $\gamma$ is a specifal 1-form which maps the normal of the plane to the normal (orthnormal complement) of the 2-form.

## Differential Forms and Hudge Star

In the 3 dimensional real space $\mathbb{R}^3$, the 1-forms orthnormal basis is defined as: $$dx^1, dx^2,dx^3$$
- Note this came from the note of [[1-Forms and vectors]] as the representation of basis, not the derivatives

The 2-form basis are defined like the 2-vector basis we have seen before, as: $$\alpha \land \beta = (\alpha_{i} dx^i)\land(\beta_{j} dx^j) = \alpha_{i}\beta_{j}dx^i \land dx^j$$
Since the real parts evaluates to 1 and selfwedging are canceled out, we have:
$$\begin{align}
&0&&dx^1 \land dx^2&&-dx^3\land dx^1 \\
&-dx^1\land dx^2 &&0&&dx^2 \land dx^3 \\
&dx^3\land dx^1&&-dx^2\land dx^3&&0
\end{align}$$
However since we have negative and positive versions of wedge products, we only have 3 distinctive basis for the 2-forms, as:

![[Screenshot from 2023-03-23 12-49-08.png]]

And the 3-form basis in $\mathbb{R}^3$ has only one element:
$$dx^1 \land dx^2 \land dx^3$$
Note in practice, the number of k-form basis is defined by therule of combination with binomial coefficients, as:
$$\frac{n!}{k!(n!-k!)}$$
And the hudge star of these basis would be the orthogonal complements, with the dimension of n-k following the same rule. For any flat space we have the equations:
$$\star(dx^{i_{1}} \land dx^{i_{2}}\land\dots \land dx^{i_{k}}) = dx^{i_{k+1}} \land\dots \land dx^{i_{n}}$$
where $i_{1},\dots,i_{n}$ is the even permutation of $(1,..,n)$

## K-Forms in non-flat space

For a surface mapping $f:\mathbb{R}^2 \subset M \to \mathbb{R}^3$ there exists orthnormal vectors $u,v \in \mathbb{R}^2$ , the output vectors from the mapping would be a vectors $df(u), df(v)$. Like in the following graph:

![[Screenshot from 2023-03-23 13-02-00.png]]

However, note that the region we care about is also "stretched" by this nonlinear mapping of the surface, therefore we will not have $dx^1 \land dx^2 (u,v)=1$ (or this will just give us the area of the plane formed by these two original vectors)vectors instead of the warpped surface

The induced metric $g$ of the vectros over the mapping is defined through the dot products of the embedded vectors, as: $$g(u,v)=df(u) \cdot df(v)$$
The determinant of the metrix is defined as: $$\det(g) := g(u,u) g(v,v) -g(u,v)^2$$
We can expand this as $$\det(g) = (df(u) \cdot df(u)) \cdot (df(v)\cdot df(v)) - (df(u) \cdot df(v))^2 $$
Note that the dot product of the vector against itself gives us the squared  norm of the vector:
$$\det(g) = | df(u)|^2 |df(v)|^2 -(|df(u)||df(v)| \cos \theta)^2$$
By rearranging the terms we will achieve a conclusion that:
$$\det(g) = (|df(u)| |df(v) | \sin \theta)^2 = |df(u)\times df(v)|^2$$
And therefore, we have an extremely neat conclusion for the 2-from over mappings, as:
$$w := \sqrt{ \det(g) } dx^1 \land dx^2$$
- Here $\omega$ is defined as the "volume" form over the curve space.

More generally, we have the following conclusion: $$\omega  := \sqrt{ \det(g) } dx^1 \land \dots \land dx^n$$
In the curved space, the hudge star will also capture the fact of the stretching effect, where we have the following operation, as $w$ is clearly the "unit volume" in the curved space:
$$\star 1 = w$$
The k-forms also have an defined inner-product operation, as we have any n-form containing a pair of k-forms $\alpha$ and $\beta$ satisfies :
$$\alpha \land \star \beta = \langle \langle \alpha , \beta \rangle  \rangle w$$
Where the inner operation is jsut the dop product among the k-forms:
$$\langle \langle \alpha, \beta \rangle  \rangle : \sum_{i} \alpha_{i} \beta_{i}$$
