----
- Reference [[T-Topology]]
## Continous Mapping

A mapping $f:X\to Y$ between two topological spaces is said to be continuous if $$\forall U \subset_{open} Y, f^{-1}(U) \subset_{open}X$$
- Which means for a open set in $Y$, its pre-image must be open set in $X$

#### Examples

Examples, if we define the discrete topology $\mathcal{T} = \mathcal{P}(X)$ on set $X$ , assume there exists $f: X\to Y$ to be a mapping, we have: $$\forall U \subset_{open}Y, f^{-1}(U)\subset_{open}$$
And this implies that all mappings from a discrete topology will be continuous

Example 2: if we define the trivial topology $\mathcal{T} = \{ \emptyset, X \}$ , assume there exists $f:X\to Y$ as a continous mapping. If $f(X)$ is the image of $X$ , $f(X)\subset Y$, due to subspace topology, the mapping $$f:X\to f(X)$$ is also a continuous mapping. 

Note that, if $X$ is a trivial topological space and $f:X\to f(X)$ is a continuous mapping, then $f(X)$ must also be a trivial topology space. 

