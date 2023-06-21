----
Given two [[Banach Space]] $X$ and $Y$ (over the same scalar field, typically real or complex numbers), a linear operator $T: X → Y$ is called a bounded linear operator if there exists a constant $C > 0$ such that for all $x$ in $X$, the following inequality holds:$$||T(x)||_Y ≤ C * ||x||_X$$Here, $||x||_X$ and $||T(x)||_Y$ denote the norms of the vectors $x$ in $X$ and $T(x)$ in $Y$, respectively.

In other words, a linear operator is bounded if it does not stretch the elements of the domain vector space $X$ by more than a constant factor $C$ when mapping them to the codomain vector space $Y$. This constant $C$ is also called the operator norm of $T$ and is denoted as $||T||$.

The set of all bounded linear operators from $X$ to $Y$ is denoted as $L(X, Y)$ or $B(X, Y)$. This set, equipped with the operator norm, forms a Banach space. It means that $L(X, Y)$ is a complete normed vector space, which implies that every Cauchy sequence of bounded linear operators in $L(X, Y)$ converges to a limit within the space.
