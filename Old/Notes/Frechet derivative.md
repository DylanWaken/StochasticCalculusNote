----
The implicit function theorem states the fact that, for a multivarialte function of multiple parameters, the function implivitly defined correlations between the parameters.

## Fréchet Differentiability

The origional definition of Frechet derivative is that, for some function $f(x)$, we do the linear approximation of the function through an linear term (as some function times epsilon) with some small change due to the nonlinearity of the function, as: $$f(x+\epsilon)= f(x) + f'(x)\epsilon+ o(\epsilon)$$
- Where $o(\epsilon)$ is some smaller term compared to $\epsilon$ and converges to zero in faster in a complexity level compared to $\epsilon$
- The function in the linear term is called the Frechet derivative of the function.

Let $X$ and $Y$ be two Banach spaces and denote by $L(X, Y )$ the space of [[bounded linear operators]] $X → Y$ . For example, if $X = \mathbb{R}^n$, $Y = \mathbb{R}^m$, then $L(X, Y )$ can be identified with the space of $m × n$ matrices with real entries.

Let $F:U \subset X\to Y$ be a continuous function (where $U$ is a subset of $X$). The map $F$ is said to be differentiable at $u \in U$ if there exists $T \in L(X,Y)$ such that: $$\lVert F(u_{0} +h) -F(u_{0}) - Th\rVert _{Y} = o(\lVert h \rVert )_{X} ,h\to 0_{m\times n}$$
- $T$ is an element of the space of bounded linear operators $L(X, Y)$, meaning that it maps elements from the normed vector space $X$ to the normed vector space $Y$ while preserving linearity. The operator $T$ **is called the Fréchet derivative of $F$ at the point** $u₀$.
  
- The reason $Th$ is included in the definition is to capture the linear approximation of the function $F$ at the point $u₀$. If $F$ is differentiable at $u₀$, then $Th$ provides an linear approximation to the change in $F$ when moving from $u₀$ by a small amount in the direction of $h$. 
  
- The term $o(‖h‖_X)$ represents the little-o notation, which captures the limiting behavior of a function as its argument approaches zero. In this context, $o(‖h‖_X)$ is a function of h such that the limit of the ratio of $o(‖h‖_X)$ to $‖h‖_X$ goes to zero as $h$ goes to zero: $$\lim _{h → 0} (o(‖h‖_X) / ‖h‖_X) = 0$$
- Using the definition above, we can rewrite this function as: $$\lim_{ h \to 0 } \frac{1}{\lVert h \rVert_{X}} \lVert F(u_{0}+h) -F(u_{0}) - Th ||_{Y} = 0$$
Loosely speaking, a continuous function is differentiable at a point if, near that point, it admits a “best approximation” by a linear map.

When $F$ is differentiable at $u_{0} ∈ U$ , the operator $T$ in the above definition is uniquely determined by: $$Th = \frac{d}{dt} |_{t=0} F(u_{0}+th) = \lim_{ t \to 0 } \frac{1}{t} (F (u_0 + th) − F (u_{0}))$$
We also denote the derivative term as: $T = D_{u_{0}}F \in L(X,Y)$

Note: for a function between $\mathbb{R}^m$ and $\mathbb{R}^n$ , the derivative operator at point $p$ is given as the Jacobian matrix of function $F$ evaluated at $p$.

Note that $D_{u_{0}}F$ will be a extremely good local approximation of the function around a point.
