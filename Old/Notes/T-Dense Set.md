----
Definition: let $X$ be a topological space (see [[T-Topology]]),   $A\subset X$ is a dense subset if and only if $\bar{A} = X$ (the closure of the subset is the entire topological space)

For example, the set of rational numbers  $\mathbb{Q}$ is dense in the set of all real numbers $\mathbb{R}$ 

For a set $U \subset X$. we can assign the subspace topology to $U$, and therefore we can define a subset $U_{0}\subset U$ to be dense in $U$ 

Let $X$ be a topological space, $Y\subset X$ as a subsapce of $X$.  We have a set $Z \subset Y$. we define:
$$\begin{align}
&\bar{Z_{Y}} : \text{The closure of Z in Y} \\
&\bar{Z_{X}} : \text{The closure of Z in X}
\end{align}$$
And there is a fact that: $$\bar{Z_{Y}} = \bar{Z_{X}} \cap Y$$
**Let $X$ be a topological space, $F \subset X$ is a dense set, $U \subset_{open} X$, then $F\cap U$ is dense in $U$**

Proof: $\bar{F \cap U}_{u} = U \iff U \subset \bar{(F \cap U)_{X}}$

Prove : $\forall x \in U, x \in \bar{F\cap U}_{X}$ 
Case 1: $x \in F \cap U \implies x \in \bar{F\cap U}_{X}$
Case 2: $x \notin F \cap U$, prove that $x$ is a accumulation point of $F \cap U$ in $X$

- This is the same as provie $\forall V \subset_{open} X (x\in V), V \setminus\{x  \} \cap (F \cap U) \neq \emptyset$ 
- By transforming we have $((V\cap U)\setminus \{x \}) \cap F$ , since $V\cap U$ is a open set, the expression is not a empty set as $F$ is a dense set and $x$ is not in $F$, means $x$ must be an accumulation point of $F$.  By definition, $x$ is acclumulation point of $F$ in $X$ 

## Points

Definition: Let $X$ be a topological space, $A\subset X$, then :

**Interior point:** $int(A) := \{ p\in A : \exists V \subset_{open} X,p\in V, V \subset _{\neq } A\}$
**Exterior point:** $ext(A):=\{ p \notin A : \exists V \subset_{open}X, p\in V, V \subset_{\neq} X \setminus A \} = int(X\setminus A)$
**Boarder point:** $\partial(A) := \{ p \notin A : \exists V \subset_{open}X, p\in V, V \cap A \neq \emptyset,V\cap X\setminus A \neq \emptyset\}$

This also means $X=int(A) \coprod ext(A) \coprod \partial A$ , where $\coprod$ is the Coproduct, or the union of non-intersecting sets.

