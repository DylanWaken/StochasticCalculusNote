------
### Subspace:

Let $X$ be a topological space, and let $S \subseteq X$ be any subset. We define a topology $\mathcal{T}_{S}$ by: $$\mathcal{T}_{S} = \{ U \subseteq S : U = S \cap V ,V\in \mathcal{T}_{X}\}$$
In other words, the open subsets of $\mathcal{T}_{S}$ are the intersections with $S$ of the open subsets of $X$

> Exercise 3.1: Prove topology
> 1: $\varnothing \cap S = \varnothing \implies \varnothing \in \mathcal{T}_{S}, X \in \mathcal{T}_{X},S\cap X=S \implies S\in \mathcal{T}_{S}$
> 2: $U_{1},U_{2} = V_{1} \cap S, V_{2}\cap S, V_{1},V_{2} \in \mathcal{T}_{X}\implies V_{3} = V_{1} \cap V_{2} \in \mathcal{T}_{X}$
> $U_{1} \cap U_{2} =V_{1}\cap V_{2} \cap S=V_{3}\cap S,V_{3} \in \mathcal{T}_{X} \implies U_{1} \cap U_{2}  \in \mathcal{T}_{S}$ 
> 3: $i\in I,V_{i}\in \mathcal{T}_{X} \implies\bigcup_{i} V_{i} \in \mathcal{T}_{X},V_{i} \cap S \in \mathcal{T}_{S} \implies\bigcup_{i}(V_{i}\cap S) \in \mathcal{T}_{S}$  

This topology is called **Subspace Topology**. A subset of a topological space $X$ , considered as a topological space with the subspace topology, is called a **subspace of** $X$

> **Exercise 3.2: Suppose $S$ is a subspace of $X$. Prove that a subset $B \subseteq X$ is closed in $S$ if and only if it is equal to the intersection of $S$ with some closed subset of $X$ .**
> Left to Right:
> if $B'$ is a open set in $X$, $B\neq S, B' \neq \varnothing$, and $B =B' \cap X$,  then by the definition of subspace topology, $B \in \mathcal{T}_{S}$.  $B$ is open in $S$, and thus $B$ is not closed. Proved by contradiction.
> For the excluded cases, since $S,\varnothing$ are both closed and open, claim satisfies
> Right to Left:
>  $B'$ is closed in $X$, $B = B' \cap S, B' \neq X,B' \neq \varnothing, B \neq S$. Since $B'$ is not open $X$, $B' \cap S$ is not in the topology $\mathcal{T}_{S}$ . Therefore, $B' \cap S$ is closed in $S$.
>  For the excluded cases, since $S,\varnothing$ are both closed and open, claim satisfies

> **Exercise 3.3: Let $M$ be a metric space, and let $S \subseteq M$ be any subset. Show that the subspace topology on $S$ is the same as the metric topology obtained by restricting the metric of $M$ to pairs of points in $S$ .**
> If $(M,\mathcal{T},d)$ is a metric space, then the topology on $S$ is obtained by definition as  $$\mathcal{T}_{S} = \{ U \subseteq S : U = S \cap V ,V\in \mathcal{T}\}$$
> Since all open sets in $M$ can be viewed as the union of open balls from the metric, therefore for all open sets $V = V' \cap S,V\subseteq S$, there exists some open balls under the same metric $B_{i},i\in I,B_{i}\subseteq M, B_{i}\subseteq S$ such that $\bigcup_{i}B_{i}=V$. Therefore, it is equivalent to the metric induced topology space on $S$ by $d_{M}$ 

A set $U \subseteq S$ is **relatively open or relatively closed** in $S$ if $S$ is a subspace of $X$. This means that the "closed" or "open" descriptions would be relative to the subspace topology instead of the main one.

A neighborhood of $x$ in $S$ in the subspace topology is sometimes called a **relative neighborhood** of $x$

**Proposition:** 

- A) If $U \subseteq S \subseteq X$, $U$ is open in $S$, and $S$ is open in $X$, then $U$ is open in $X$. Note that this works if we replace all "open" with "closed".
- B) If $U$ is a subset of $S$ that is either open or closed in $X$, then it is also open or closed in $S$ , respectively.

> **Exercise 3.6: Proof**
> a) $U$ open in $S \implies$ $U \in \mathcal{T}_{S}$. Since $S$ is open in $X$, that means for all $U \in \mathcal{T}_{S}$, $U \in \mathcal{T}_{X}$ by definition of subset topology. (similar proof for closed)
> b) $U \subseteq S$, if $U$ is open, then by definition $U$ will be open in $S$, same for closed. if $U=S$, then $U$ can be either open or closed in $S$, which makes it satisfies the proposition.

> **Exercise 3.7**. Suppose $X$ is a topological space and $U \subseteq S \subseteq X$.
> a) The closure of $U$ in $S$ is equal to $\bar{U} \cap S$
> b) The interior of $U$ in $S$ contains $IntU \cap S$; give an example to show that they might not be equal.
> Show  $\overline{U \cap S}=\bar{U} \cap S$: Since $\overline{U \cap S}= \bar{U} \cap \bar{S}$, and in subspace topology we have $\bar{S}=S$, therefore the proposition holds.
> Show $Int(U \cap S) \supseteq Int U \cap S$ Counter example. If $U$ is a closed subset of $X$, and $S$ is also closed in $X$, and $U$ shares boundary with $S$, then the interior of $U$ intersect with $S$ would not include the boundary points. However, for $Int U\cap S$, since $S$ is open in $S$, then these boundary points would be included.

 **Characteristic Property of the Subspace Topology:** Suppose $X$ is a topological space and $S \subseteq X$ is a subspace. For any topological space $Y$ ,a map $f:Y\to S$ is continuous if and only if the composite map $\iota_{S} \circ f:Y\to X$ is continuous. (Proof in page 51 of the book)

$\iota_{S}$ is the "inclusion map" in topology, $A\subseteq B,\iota_{}:A\to B,\iota(x) \to x$, it is a identity map from a subset to the superset.

**Corollary**: If $S$ is a subspace of the topological space $X$ , the inclusion map $\iota_{S}:S\to X$ is continuous.

**Corollary**: Let $X,Y$ be topological spaces, and suppose $f:X\to Y$ is continuous. 

- a) RESTRICTING THE DOMAIN: The restriction of $f$ to any subspace $S \subseteq X$ is continuous.
- b) RESTRICTING THE CODOMAIN: If $T$ is a subspace of $Y$ that contains $f(X)$, then $f:X\to T$ is continuous.
- c) EXPANDING THE CODOMAIN: If $Y$ is a subspace of $Z$, then $f:X\to Z$ is continuous.

**Additional Properties:**

- If $R \subseteq S$ is a subspace of $S$ , then $R$ is a subspace of $X$ ; in other words, the subspace topologies that $R$ inherits from $S$ and from $X$ agree.
- If $\mathbf{B}$ is a basis for the topology of $X$, then: $$\mathbf{B}_{S} = \{  B \cap S : B \in \mathbf{B}\}$$ is a basis for the topology of $S$
- If $\{  p_{i} \}$ is a sequence of points in $S$ and $p \in S$, then $p_{i}\to p$ in $S$ if and only of $p_{i}\to p$ in $X$
- Every subspace of a Hausdorff space is Hausdorff.
- Every subspace of a first countable space is first countable
- Every subspace of a second countable space is second countable.

> Exercise 3.12:
> (c) : if for every neighborhood $U$ of $p$ there exists $N \in \mathbb{N}$ such that $x_{i} \in U$ for all $i>N$, that means for $U \subseteq S$, there exists the further sequence of points defined above. Since $U \subseteq X$, the series is also converging in $X$. (The converse is also easily proven, skipped)
> (d) : By the definition of subspace topology and hausdorff space, for all point $p_{1},p_{2} \in X$, there exists $U_{1},U_{2},x_{1}\in U_{1},x_{2} \in U_{2}$ such that $U_{1} \cap U_{2} = \varnothing$. We also have: $p_{1},p_{2}\in S$ and other sets $U_{1}\cap S \cap U_{2}\cap S =(U_{1}\cap U_{2}) \cap S=\varnothing$ . Therefore, the subspace of hausdorff space is hausdorff
> (e): First countable means every point have a countable neighborhood basis. Since every point in $X$ have a countable neighborhood basis, then every point in $S$ would have a countable basis of the same sets intersecting $S$. Thus the property maintained
> (f): Similar to (e) but for the entire topological basis

### Topological Embeddings

An **injective continuous map that is a homeomorphism onto its image** (in the subspace topology) is called a **topological embedding** (or just an embedding). If $f:A\to X$ is such a map, we can think of the image set $f(A)$ as a homeomorphic copy of $A$ inside $X$.

A continuous injective map might or might not be an embedding. It is not always easy to tell whether a given map is or is not an embedding.

**Proposition**: A continuous injective map that is either open or closed is a topological embedding.

> Exercise 3.17: Example of a topological embedding that is neither open or closed
> Example: (FAILED)

**Proposition**: A surjective topological embedding is a homeomorphism.
 
> Exercise 3.19: Proof of proposition:
> if $f:A\to X$, is a injective continous map, and the map $f: A\to f(A)$ is a homeomorphism. Then since $f$ is also surjective, that means $X \subseteq f(A)$. This makes $f$ a bijective map, and a homeomorphism from $A$ to $X$

Note that, A subspace of some second countable hausdorff space is also second countable hausdorff, which means to varify the subspace is a manifold, we only have to check it is locally Euclidean.

**Gluing Lemma:** Let $X$ and $Y$ be topological spaces, and let $\{ A_{i} \}$ be either an arbitrary open cover of $X$ or a finite closed cover of $X$ . Suppose that we are given continuous maps $f_{i}:A_{i}\to Y$ that agree on overlaps: $f_{i}|_{A_{i}\cap A_{j}}=f_{j}|_{A_{i}\cap A_{j}}$ Then there exists a unique continuous map $f:X\to Y$ whose restriction to each $A_{i}$ is equal to $f_{i}$ .