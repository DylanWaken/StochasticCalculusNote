----

## Topology

Definition: :Let $X$ be a set with $\mathcal{T}$ being a family of subsets of $X$ (we call the elements of $\mathcal{T}$ as the open sets in $X$), satisfies :

- $\emptyset \in \mathcal{T}$ , $X \in \mathcal{T}$ are open sets
- $U,V$ are open sets, then $U \cap V$ is a open set (arbitrary intersections)
- $U_{\alpha}, \alpha\in I$ is open set, then $\bigcup_{\alpha \in I} U_{\alpha}$ is a open set (finite (countable) union)

When these conditions are satisfied, we call $\mathcal{T}$ a topology over set $X$ 

The elements of a topology are called open sets.

There is also a set of rules for closed sets (using De-Morgan's law):

- $\phi, X$ are closed sets
- $\forall U,V$ closed, $U \cup V$ is closed under arbitrary unions
- $\forall U_{\alpha}$ closed, $\alpha \in I$ ,  $\bigcap_{\alpha \in I} U_{\alpha}$ is closed under finite (countable) intersections

## Open Set

A openset $U$ in a metric space is defined as the set that for any point $p\in U$, there exists a open ball $B$ (all points less than radius r to p) of radius $\delta >0$ such that: $$B(p: \delta) \subset U$$
When there exists no metirc, the open sets are defined as the element of a topology. 

The complement of a open set is a closed set, as:
$$U \in \mathcal{T} \implies U^c \notin \mathcal{T}$$
- Note that for a set $X$, there exists an exception which topology elements $\emptyset, X$ are both closed sets and open sets, since they are the complements of each other.

The **Interior** of a set $A$ is defined as the union of all opensets contained in $A$, as:
$$A^o := \bigcup_{U\in \mathcal{T}, U\subseteq A} U$$
- This is also known as the largest possible open set contained in $A$
- If $A$ is a open set, then the interior of $A$ is itself. else the interior is the set $A$ subtract its boundry

The **closure** of a set $A$ is defined as the intersection of all closed sets containing $A$, as:
$$\bar{A} := \bigcap _{E^c \in \mathcal{T},A \subseteq E} E$$
- This is also known as the smallest possible closed set containing $A$
-  If $A$ is a closed set, then the closure of $A$ is itself. else the closure is the set $A$ union its boundry
- $\bar{A}$ is also the union of $A$ and all its accumulation points.
- Property : $\bar{A\cup B} = \bar{A} \cup \bar{B}$, $\bar{A \cap B} \subset_{proper} \bar{A} \cap \bar{B}$

The **boundary** of a set $A$ is defined as the closure of the set excluded its interior, or:
$$\partial A = \bar{A} / A^o = \bar{A} \cap \bar{A^c}$$
- If $A \subseteq X,\bar{A} = X$, then we say $\bar{A}$ is a **dense** set of $X$.

If $E\subseteq X$, The **neighborhood** of $E$ is a set $A$ such that $E \subseteq A^o$. Therefore, **a set $A$ is a open set if and only if $A$ is the neighborhood of itself.** 

The **Accumulation point (limit point)** of a set $A$ is the point $x$ if $A \cap (U \setminus\{ x \}) \neq \emptyset$ for every neighborhood $U$ of $x$

- In another way of saying,  any arbitrarily small region around $x$ must interset with set $A$ to be considered an accumulation point of $A$, it can be inside the set or on the boundry of $A$.

## Closed sets

Let $X$ is a topological space, $A\subset X$, then $A$ is a closed set if and only if $\bar{A} = A$, or the closure of $A$ is the same as itself. This also means all accumulation point $\forall x:A \cap (U \setminus\{ x \}) \neq \emptyset, x\in A$ 

Let $A$ is a closed set, we have to prove that $A = \bar{A}$ , we have to prove that $X \setminus A \subset X  \setminus \bar{A}$
, which is prve that every point not in $A$ is not its accumulation point. 

- Since $A$ is closed set, $X \setminus A$ is a open set, $\implies$ $\exists$ open set $U \subset X \setminus A, p\in U$ . This implies $U \setminus \{ p \} \cap A = \emptyset$ , which proves $p$ is not an accumulation point.

Let $\bar{A} = A$, prove $A$ is a closed set. We have to prove that $X \setminus A$ is a open set. $\forall p \in X \setminus A$ , to prove there exists open set $U$ that satisfies $p\in U \subset X\setminus A$. 

- $p\notin A \implies p \notin \bar{A} \implies p$ is not accumulation point of $A \implies \exists$ openset $U \subset X$  such that $U \setminus \{ p \} \cap A = \emptyset \implies U \in X\setminus A$ , proved.


## Topological space

**$(X,\mathcal{T})$ is called a topological space. When we say let $X$ be a topological space, $X$ is a set and we assigned a topology of $X$ (by indicating the subsets that are open sets)**

A **trivial topology i**s defined as  $\mathcal{T} = \{\emptyset ,\mathbb{R}^n \}$ - smallest topology
A **discrete topology** is defined as  $\mathcal{T} = \mathcal{P}(X)$ - largest topology (covers all possible subsets of $X$)

For example, prove $\mathbb{R}^n$ is a topological space with trivial topology $\mathcal{T} = \{\emptyset ,\mathbb{R}^n \}$
1: The first property automatically satisfied by definition.
2: Let $U,V$ be open sets in $X$, prove $U \cap V$ is a open set:
$$\begin{align}
&\forall p \in U\cap V\implies p\in U, p\in V \\
&\exists \delta_{1}>0,s.t. p\in B(p:\delta_{1}) \subset U \\
&\exists \delta_{2} > 0, s.t. p\in B(p:\delta_{2})\subset V
\end{align}$$
If we choose the minimal value of $\delta$ above, we would reach the following conclusion that:
$$B(p:\delta) \subset U, B(p:\delta)\subset V$$
in which we have proved $U \cap V$ is a open set

3: Let $U_{\alpha}, \alpha\in I$ be a open set, prove $\bigcup_{\alpha=I} U_{\alpha}$ is open set:
$$\begin{align}
&\forall p \in \bigcup_{\alpha \in I} U_{\alpha}\implies \exists \alpha\in I,p\in U_{\alpha} \\
&\exists \delta < 0,s.t.p\in B(p:\delta) \subset U_{\alpha}\\ 
&U_{\alpha} \subset \bigcup_{\alpha\in I} U _\alpha \implies  p\in B(p:\delta) \subset\bigcup_{\alpha\in I} U _\alpha
\end{align}$$
Therefore we have prove it to be open set.

**Different topologies (topological spaces) can be assigned to the same set.**

## Induced Topology of Metric Space

A metric space is defiend as a distance function defined upon the elements of a set $X$ such that:
$$d: X\times X\to \mathbb{R}, (X_{1},X_{2})\to d(X_{1},X_{2})$$
The distance have the following property:

- 1: $d(x,y)\geq 0, d(x,y)=0 \iff x=y$
- 2: $d(x,y) = d(y,x)$
- 3: $d(x,y) \leq d(x,z)+d(z,y)$

And we call $(X,d)$ a metric space.

The metric space can induce a topology over $X$, as we can define the open ball on set $X$ as:
$$B(x_{0}:\delta) = \{ x \in X:d(x,x_{0}< \delta) \}$$
And then we can define the open set on set $X$

The set of all open sets $\{ U:U \subset X\}$ defined a topology on set $X$. This topology is called the induced topology of the metric space.

## Subspace topology

Let $X$ be a topological space, $Y \subset X$, we define topology $F:= \{ U \cap Y : U \subset_{open}X \}$, then $F$ is a topology on $Y$, and we call this a induced topology of $X$ on $Y$ , where $(Y,F)$ is called the topological subspace of $X$

Proof of $\{ U \cap Y : U \subset_{open}X \}$ as topology on $Y$:

-  1 : $\emptyset = Y \cap \emptyset$ , and as $X$ being a topological space, $\emptyset$ is open in $X$, so the empty set is open in $Y$ $Y=Y\cap X$ and $X$ is open in $X$ through the definition of topological space, so $Y$ is open in $Y$ 

- 2: Take any $U_{1},V_{1} \subset_{open} Y$ ,  we can rewrite the open sets as: $$U_{1}= Y \cap O_{1}, V_{1} =Y\cap O_{2}$$ where $O_{i}\subset_{open}X$ . Now, the intersection of the open sets are written as: $$U_{1}\cap V_{1} = (Y\cap O_{1}) \cap (Y\cap O_{2}) = Y \cap(O_{1}\cap O_{2})$$ since $X$ is topological space, $O_{1} \cap O_{2}$ is a open set in $X$, then this set is also open in $Y$, second property proved

- 3: Take any collection of open sets in $Y$, $\{ U_{\alpha} \}_{\alpha \in I}$ . Then for each $\alpha\in I$, $\exists O_{\alpha}\subseteq_{open} X$ such that $$U_{\alpha} = Y \cap O_{\alpha}$$ Then the union can be rewritten as: $$\bigcup _{\alpha\in I} U_{\alpha} = \bigcup_{\alpha\in I} Y \cap O_{\alpha} = Y \bigcap (\bigcup_{\alpha\in I} O_{\alpha})$$ since the later part is a open set in $X$ due to $X$ being a topological space, therefore the union of the open subsets of $Y$ is also a opensubset of $Y$
