----
An open neighborhood is a concept from topology that refers to an open set containing a specific point. Given a topological space $(X, τ)$ and a point $x ∈ X$, an open neighborhood of $x$ is an open set $U$ that belongs to the topology $τ$ and contains the point $x$. 

It is important to note that the term "neighborhood" is sometimes used more broadly to refer to any subset of the topological space containing an open set that contains the point $x$.

**Theorem:** Let $X, Y , Z$ be [[Banach Space]], $U ⊂ X, V ⊂ Y$ be open sets and $$F :U ×V →Z$$be a smooth map. Let $(x_{0}, y_{0}) ∈ U × V$ and $z_{0} := F (x_{0}, y_{0})$. Set $$F_{2} : V → Z, F_{2}(y) = F (x_{0}, y).$$ Here we need to use the [[Frechet derivative]]. Assume that $D_{y_{0}}F_{2} \in L(Y,Z)$ is invertible. Then there exist open neighborhoods $U_{n} ⊂ U$ of $x_{0}$ in $X$, $V_{n} ⊂ V$ of $y_{0}$ in $Y$ , and a smooth map $G : U_{n} → V_{n}$ such that the set $S$ of solution $(x, y)$ of the equation $F (x, y) = z_{0}$ which lie inside $U_{n} × V_{n}$ can be identified with the graph of $G$, : $$\{ (x, y) ∈ U_{n} × V_{n} ; F (x, y) = z_{0} \} = \{ (x, G(x)) ∈ U_{n} × V_{n} ; x ∈ U_{n} \}.$$ > Proof in the book

