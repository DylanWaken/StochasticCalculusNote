----
## Base Concepts

A topological space defined **How points are connected/related to each others without defining their exact locations**. 

A **convex set** is defined as: a subset $S \subset \mathbb{R}^n$ is convex is for every pair of points $p,q \in S$, all points belong to the line segment between the points are also contained in $S$.  

A **convex hull** is defined as for subset $S \subset \mathbb{R}^n$, its convex hull $conv(S)$ is the smallest convex set containing $S$, or equivalently, the intersection of all convex sets containing $S$.

A collection of $k+1$ points $p_{0},\dots,p_{k}$ that are **affinely independent** if the vectors $v_{i} := p_{i}-p_{0}$ are linearly independent.

A **k-simplex** is the convex hull of $k+1$ affinely-independent points, which we call **vertices**. The affine independence ensures all points to be verticies of the convex hull.

- Note: the degree of the simplex is at maximum dimension of the space

A **barycentric coordinate** manes that any point $p$ in the simplex can be written as a non-negative linear combination of the weighted vertices, where the weights sum to 1.
$$p = \sum_{i=0} ^k w_{i}p_{i}\quad s.t. \quad\sum_{i=0} ^k w_{i} = 1, w_{i}\geq 0$$
And therefore, the simplex itself can be represented as all possible non-negative linear combinations of the vertices, as:
$$\sigma = \left\{  \sum_{i=0}^k w_{i}p_{i} :\sum_{i=0}^k w_{i}=1, t_{i} \geq 0 \forall i  \right\}$$
These weigths are called the **barycentric coordinates**, and the non-negative property make this combinations **convex combinations**.

A standard n-simplex is the collection of points:
$$\sigma := \left\{  p=(x_{0},\dots,x_{n})\in\mathbb{R}^{n+1} : \sum_{i=1} ^n x_{i} = 1, x_{i}\geq 0 \forall i\right\}$$
- Note, $x_{i}$ are the coordinates values of point. $x_{0} = 0$
- This simplex is also called the **probability simplex**

## Simplicial Complex

A simplicial complex is the collection of simplicies. 

A **face** of a simplex $\sigma$ is any simplex whose vertices are a subset of the vertices of $\sigma$. (Note: including the simplex itself). The empty set is also a face.

A **geometrical** **simplicial complex** is a collection of simplices where:

- The intersection of any two simplices is a simplex
- every face of every simplex in the complex is also in the complex

![[Screenshot from 2023-03-11 11-03-46.png]]

An **Abstract Simplicial Complex** is a collection of sets. If for each $\sigma \in S$ all subsets of $\sigma$ are contained in $S$, then $S$ is an abstract simplicial complex. 

![[Screenshot from 2023-03-11 11-08-24.png]]

This is an example of topological space.
An undirected graph is a 1-abstract-simpliex with vertices and edges

**Closure** is the smallest simplicial complex containing a given set of simplices. 

**Star** is the union of simplices containing a given subset of simplices

**Link** is the closure of the stars minus the star of the closure.

![[Screenshot from 2023-03-11 11-26-56.png]]

For simplicial 1-complexes (Graphs), the definition is the set of vertices and edges:
$$G = \{ V,E \}$$
For simplicial 2-complexes (Triangle Meshes), we often define it as vertices, edges and faces (geometric faces, not the simplicial faces):
$$G=\{ V,E,F \}$$
## Orientation of simplicial complex

THe orientation of a 1d k-simplex is the direction of connection between the two vertices:
$$a\to b, b\to a$$
There are only two cases.

The orientation of a 2d k-simplex is defined as the "winding order" of the simplex over the 3 vertices. as:
$$1:(a,b,c),(b,c,a),(c,a,b),2:(c,b,a),(b,a,c),(a,c,b)$$
There are 2 orientations described by 6 tuples. The circular shifts describe the same oriented 2-simplex/ Normally we can choose the easiest one to be the "**representative ordered tuple**" of the orientation. 

For the orientation of a k-simplex, **An oriented k-simplex is an ordered tuple, up to even permutation**. (even numbers of swaps of elements in the tuple, which will not change the "order" of the tuple)

We always have two orientations, by having even and odd permutations. we says even permutations of $(0,\dots,k)$ to be "positive", and others to be "negative"

The 0-simplex have only one positive orientation. 

An **oriented simplicial complex** is the simplicial complex where every simplex in it is given an specific ordering.  

![[Screenshot from 2023-03-11 21-22-15.png]]

Two distinct oriented simplices have the same **relative orientation** is the two maximal faces in their intersection have opposite orientation. (Note the second example above, the edge $bc$ fits both triangles)

## Persistent Homology Analysis

Persistent Homology analysis understrand data using connectivity. They track the persistance of simplices over the data points through time by applying some modifications to construct/deconstruct simplicies.  

![[Screenshot from 2023-03-11 11-19-22.png]]

The existance of divergence fo diagnal explanes features of the data. When divergences are strong, the features are likely to be real. 

