----
A homeomorphism is a continuous, bijective mapping between two topological spaces that has a continuous inverse.

An open cover of a topological space $X$ is a collection of open sets $\{U_i\}$ such that the union of these open sets contains the entire space $X$, i.e., $X ⊆ ⋃ U_i$. In other words, the open sets in the open cover "cover" the whole space without any gaps.

![[Screenshot from 2023-04-16 19-52-22.png]]

**Definition:** A smooth manifold of dimension m is a locally compact, second countable1 Hausdorff space M together with the following collection of data (henceforth called **atlas** or smooth structure) consisting of the following:

- An open cover $\{U_{i}\}_{i∈I}$ of $M$ (Where $M$ is the domain)
- A collection of homeomorphisms corresponding to each of the open subsets: $$f_{i}:U_{i}\to f_{i}(U_{i}) \subset \mathbb{R}^m; i\in I$$ (called charts or local coordinates) such that, $f_{i}(U_{i})$ is open in $\mathbb{R}^m$ . where $\mathbb{R}^m$ is the space that the charts is embedded in.  if $U_{i} ∩ U_{j} \neq ∅$, then the transition map is a smooth map defined as: $$f_{j}\circ f_{i}^{-1} : f_{i}(U_{i} \cap U_{j}) \subset \mathbb{R}^m \to f_{j}(U_{i} \cap U_{j}) \subset \mathbb{R}^m$$The homeomorphisms must agree upon the place where they intersects, in the other words it says that the overlapping parts of the charts have the same shape.  


(Note that the definition of a smooth manifold doesn't require it to be embedded in an m-dimensional Euclidean space. The reason that each homeomorphism maps an open subset $U_i$ of the manifold to an open subset of Euclidean space $R^m$ is to capture the idea that a smooth manifold is locally similar to Euclidean space.)

An **atlas** for a smooth manifold is a collection of charts that cover the manifold, allowing us to describe it in local coordinates.

Note that $\mathbb{R}^n$ is itself a smooth manifold. Its defined as an manifold of 1 atlas and 1 chart, where : $$\mathbb{1}_{\mathbb{R}^n} :\mathbb{R}^n \to \mathbb{R}^n$$
## Smooth Mappings

Let $M , N$ be two smooth manifolds of dimensions $m$ and respectively $n$. A continuous map $f : M → N$ is said to be smooth if,

- for any local charts $φ$ on $M$ and $ψ$ on $N$ , the composition $ψ ◦ f ◦ φ^{−1}$ (whenever this makes sense) is a smooth map $\mathbb{R}^m → \mathbb{R}^n$. 

A smooth map $f : M → N$ is called a **diffeomorphism** if it is invertible and its inverse is also a smooth map. (Check example 1.2.4 in first chapter) .If $M$ is a smooth m-dimensional manifold, we will denote by $C^∞(M )$ the linear space of all smooth functions $f : M → R$

