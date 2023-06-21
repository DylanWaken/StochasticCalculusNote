----
Discrete Differential Forms gives a way to solve exterior differential equations algorithmically. It works with oriented simplicial complex, and the differential k-forms are used as values stored on k-simplices, and differential operations are replaced with matrices.

## Discretization

The discretization of differential forms is done through ther de Rham map, as a way of intigrating the differential k-forms over the meth elements or oriented k-simplices.

- We apply a mesh (a k-simplicial complex) over the demain of discretization.

![[Screenshot from 2023-04-04 17-20-23.png]]

- Then we integrate the differential formand Interpolation on the mesh. in this differential 1-form case we integrate over the directed edges of the mesh, as:

![[Screenshot from 2023-04-04 18-07-09.png]]

In general, let $w$ be a differential k-form on $\mathbb{R}^n$, and let $K$ be an oriented simplicial complex. For each k-simplx $\sigma$ in $K$, the corresponding value of the discrete k-form is:
$$\hat{\omega}_{\sigma} := \int _{\sigma} \omega  $$
This map of continuous forms to discrete forms is called the **de Rham map** or discretization map

For example, integrating an differntial one form over edge is the same as:
$$\int _{e} \alpha = \int _{0}^L \alpha(T) \, ds  $$
- Where $\alpha(T)$ is applying the differential 1-form to the unit tangent of the edge at the point. We integrate this real value over the entire edge length (The curve is arc-length parameterized)

For another example, we can integrate the differential 2-form over triangled (2-simplicies) 

![[Screenshot from 2023-04-04 18-50-08.png]]

To compute the differential form over the triangle, we apply the differential 2-form onto the orthnormal basis $T_{1},T_{2}$ of the triangle (namely the 2-dimensional tangent), as:
$$\int _{t} \omega = \int _{t} \omega  (T_{1},T_{2}) \, dA \approx area(t)\left( \frac{1}{N} \sum_{i=1}^N w_{p_{i}}(T_{1},T_{2})\right)$$
- Note that apply 2 vectors on a differential 2-form would yield a real number, and we integrate that number over the area of the triangle. This measures how well the traingle lines up with the differential 2 form along its area. 
- Note this value will increase with the area of triangle, we need to devide the area if we are looking for comparation of lineup
- The order of the orthnormal basis determins the orientation of the triangle

In general, flip the orientation of the k-form would flip the sign of the integral
A discrete k-form values change sign under odd permutation (same as k-simplicies)

**Abstractly, a discrete differential k-form is the asisgnment of a value to each oriented k-simplex**

## Encoding of the Discrete Differential Form

The DDFs are encoded in an column vector with the same amount of k-simplices in the mesh, it is done by:

- 1: indexing all k-simplices under some scheme
- 2: create a column vector of the same size as number of k-simplices, and store the DDF vals inside.

Note: if we change the orientation of the k-simplex, we need also flip the value stored in the DDF vector

## Simplicial Chain and Co-chain

The simplicial chain is a integer linear combination of oriented k-simplices (free abelian group) within the simplicial complex, as:
$$\sum_{i} a_{i}\sigma_{i}:\sigma_{i}\in S$$
- Note that this "add" operation means we put the simplex into the chain.
- The non-1 indices of linear combination means copies of the same simplices in the chain. The negative indices stands for reversed orientation
- Note that the simplicial chain is also oriented
- This chain does not need to be head-to-tail "chained", it is just a subset

![[Screenshot from 2023-04-04 19-23-06.png]]

There exists arithmetics of simplicial chians, that we can fuse the chains together.

Let $\sigma := (v_{i_{0}},\dots,v_{i_{k}})$ be an oriented k-simplex, The **Boundary** is defined as the oriented (k-1)-chain :
$$\partial \sigma := \sum_{p=0}^k(-1)^p (v_{i_{0}},\dots,\setminus v_{i_{p}},\dots,v_{i_{k}})$$
- Note $\setminus v_{i_{p}}$ means that the (k-1)-simplex is omitted

The linearity allows the application of boundary operation to simplicial chains, as:
$$\partial\sum_{i} c_{i}\sigma_{i} = \sum_{i}c_{i}\partial_{i}\sigma_{i}$$
The boundary of a loop will be an empty set. Therefore taking the boundary operators on an boundary will always be empty.

The **co-boundary** of an oriented k-simplex $\sigma$ is the collection of all oriented (k+1)-simplices that contain $\sigma$, and which have the same relative orientation. It is the dual operator for co-chains, as it yields a (k+1)-chain

![[Screenshot from 2023-04-06 20-50-16.png]]

A simplicial k-cochain $\alpha$ is a **linear** map taking a simplicial k-chain to a real number. This is similar to what differential forms or co-vectors does to k-vectors.$$\alpha(c_{1}\sigma_{1}+\dots+c_{n \sigma_{n}}) = \sum_{i=1}^n \alpha_{i}(\sigma_{i})c_{i}$$
- It measures how good each weighted k-simplex lines up with each discrete differential k-form (over the same mesh) in the chain
- It is also as integrating our continous differential form over the entire chain: $$\int_{\bigcup_{{i}}\sigma_{i}} \alpha$$
## Interpolation

The interpolation of 0-forms can be done through the **Lagrange basis** $\phi$, (a real valued funtion that is linear over each simplex): $$\phi_{i}(v_{j}) = \delta_{ij}$$
- where $\delta_{ij}=(i=j)?1:0$ 
- This function only have non-zero value when evaluated on the matching vertex, therefore this function is also referred as the hat function.

Now, we can interpolate this discrete function by taking the linear combination of the hat function by vertices, as:
$$u(x) = \sum_{i}u_{i}\phi_{i}(x)$$
- $u_i$ is some weight that are assigned to each hat function
- This function would produce a continous 0-form (real values)

**Barycentric coordinate** is the way of representing each point within a k-simplex as the linear combination of all vertices, where the combined weights sums to 1:
$$\sigma = \left\{  \sum_{i=0}^k t_{i}p_{i}:\sum_{i=0}^k t_{i}=1, t_{i}\geq 0 \forall i \right\}$$
The Lagrange basis of a vertiex $i$ is given sxplicitly by the barycentric coiordinates of $i$ in each triangle containing $i$

#### Interpolate higher dimensional k-Froms

**Whitney Map** is the technique used to interpolate k-forms as:

Let $\phi_{i}$ be the hat functions on a simplicial complex, the whitney 1-forms are differential 1-forms associated with each oriented edge $ij$ given by: $$\phi_{ij} = \phi_{i}d\phi_{j} - \phi_{j}d\phi_i$$
An example looks like this:

![[Screenshot from 2023-04-07 10-14-49.png]]

And we also have:
$$\phi_{ji}=-\phi_{ij}$$
And we can interpolate any discrete 1-forms vith:
$$\sum_{ij} \hat{w}_{ij}\phi_{ijn}$$
And the interpolation on any arbitrarily dimensional whitney k-form associated with an oriented k-simplx of vertices $(i_{0},\dots,i_{k})$ is given by:
$$\sum_{p=0}^k(-1)^p \phi_{i_{p}}d\phi_{i_{0}} \land\dots \land \setminus d\phi_{i_{p}}\land\dots \land d\phi_{i_{k}}$$
