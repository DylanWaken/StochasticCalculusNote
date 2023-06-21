----
A simplicial k-complex ([[Simplex]] chapter) is **Manifold** if the **link** of every vertex looks like a (k-1)-dimensional sphere

![[Screenshot from 2023-03-12 10-50-29.png]]

Check (k=1): is the complex a closed loop
Check (k=2): is the link of every vertex a closed loop
Check (k=3): is each link a 2-sphere,  check $V-E+F=2$ (by Eular's formula)
For (k >= 3): it is a NP problem

**Manifold have predictable neighborhoods.** These would lead into topological data structures

**Adjacency list** stors all top-dimensional simplices. For example, it stores all triangle vertices (ids) of a triangular mesh. 

Pros: simple, small storage cost
Cons: hard to iterate over edges, expensive to access neighbors.

## Incidence Matrix

Let $K$ be a complicial complex, let $n_k$ denote the number of k-simplices in $K$. The $k$ th incidence matrix is a $n_{k+1} \times n_{k}$ matrix $E^k$ with entries $E_{ij}^k = 1$ if the $j$ th k-simplex is contained in the $i$ th k+1-simplex.

![[Screenshot from 2023-03-12 11-05-26.png]]

The matrix $E^0$ has all rows of the matrix correspond to an edge, and all columns correspond to a vertex. Each $1$ in the matrix stands for the containment relationship between edge and vertices (where of a edge contains the vertex, a 1 is assigned)

The matrix $E^{1}$ has all rows to be triangles and columns to be edges, the same relationship is preserved.

Note: we normally store such matrices as sparse matrix

- The common aproach is to use a **compressed column format** : we have an array of all non-zero elements, an corresponding array for row indices of these elements, and an array for comulative entries by column. (sum the number of elements in previous columns) (hard to add/remove entries, fast for operations)

## Signed Incidence Matrix

A signed incidence matrix is an incidence matrix where the sign of each non-zero entry is determined by the relative orientation of the two simplices at that row/column

![[Screenshot from 2023-03-12 11-27-49.png]]

## Half Edge Mesh

In half mesh meshes, each edge get split into two oppositely oriented half edges. 

![[Screenshot from 2023-03-12 11-31-13.png]]

- The **twin** is the other half edge on the same edge
- The **next** is another half edge that is on the same face for circulation
- The **vertex** is the vertex it came from, the **face** is the faces it belongs to.

Algebraic Definition:

Let $H$ ba any set wisth even number of elements, let $\rho : H\to H$ be any permutation of $H$, and $\eta:H\to H$ be an involution without any fixed points. Then $(H,\rho,\eta)$ is a half-edge mesh, the elemnts of $H$ are called half edges, $\eta$ are edges and the orbits of $\rho$ are faces. 

Every half edge mesh describes a compact oriented topological surface.

![[Screenshot from 2023-03-12 11-45-24.png]]

## Dual Complex

Duality stands for the existance of a dual simplex that would correspond to the original simplex, as:

![[Screenshot from 2023-03-12 11-51-49.png]]

