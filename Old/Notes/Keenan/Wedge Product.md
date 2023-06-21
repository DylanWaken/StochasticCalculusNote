----

Wedge product $\land$ between 2 vectors defines a "volume" of the two vectors with an orientation. Note this "volume" **has an magnitude (not the entire span) and a direction**, as:

![[Screenshot from 2023-03-20 10-00-42.png]]

There exists a **antisymmetry property** of wedge products as we have:
$$u\land v = -v \land u$$
The Wedge product of a vector with another vector on its span will be a plane with zero area, as:
$$u \land ku = 0 : k\in\mathbb{R}$$
![[Screenshot from 2023-03-20 10-04-48.png]]

The  Wedge product has the associability, as:
$$u \land v \land w= (u\land v)\land w = u \land (v\land w)$$

This product also have the distributive property, as:
$$u \land v_{1} + u \land v_{2} = u \land (v_{1} + v_{2})$$
The output of wedge products is called the $k-vector$.

- The k-vector only encodes the information about normal direction and magnitude. Therefore, there is no exact "shape" and "location" of the k-vectors. as long as these "planes" have the same area and direction, they are considered same k-vectors.

0-vectors is a value only have the magnitude without a direction.

The outpot of a a-vector and b-vector in wedge product is (a+b)-vector (assume these k-vectors are not on each other's spans)

## Hodge Star

The **Orthogonal Complement** of a linear subspace the span of basis vectors that are orthogonal to the basis of the linear subspace. The orthogonal complement follows a property as:
$$V:= span(\{v_{1},\dots,v_{n}  \})\to V^{\perp} := \{ v \in S : \langle v,w \rangle = 0  \forall w \in V \}$$
- Note $V \subseteq S, d\mathrm{Im}(V) = d\mathrm{Im}(S)-d\mathrm{Im}(V^\perp)$

The **Hodge Star** is like an orthogonal complement of the current k-vector, for example:
$$\star(v\land u) = w$$
- where $w$ directioned orthogonal vector of the k-vector $v$ and $u$. 

the hodge star is a function that maps a $k$ dimensional thing to a $n-k$ dimensional thing.
The Hodge star direction follows an constraint that:
$$z \land \star z$$
- The wedge product between a k-form $z$ and its hodge star is always positive oriented.

![[Screenshot from 2023-03-20 10-31-15.png]]

- An example in 2d space

## Basis and Dimensions of k-vectors

![[Screenshot from 2023-03-20 14-35-54.png]]

For a n-dimensional vector space $V$  with basis 1-vectors $\{ v_{1},\dots,v_{n} \}$. **The basis i-vectors are defined as the non-repeating i element subsets of basis 1-vectors wedge together**. Note that the non-repeating condition is order independent, it only consider whether the set contains these elements. 

For example, for $V = \mathbb{R}^4 : span\{ e_{1},e_{2},e_{3},e_{4} \}$ , we have:

basis 0-vectors : 1
basis 1-vectors : 4 $\{ e_{1}, e_{2}, e_{3}, e_{4}\}$
basis 2-vectors : 6 $\{ e_{1} \land e_{2}, e_{1} \land e_{3}, e_{1} \land e_{4}, e_{2} \land e_{3}, e_{2} \land e_{4}, e_{3}\land e_{4}\}$
basis 3-vectors : 4 $\{ e_{1}\land e_{2}\land e_{3}, e_{1} \land e_{2} \land e_{4}, e_{1} \land e_{3} \land e_{4}, e_{2} \land e_{3} \land e_{4} \}$
basis 4-vectors : 1 $\{ e_{1} \land e_{2} \land e_{3} \land e_{4} \}$

This combination actually follos the pascal triangle. Which means it for the i-th dimention the number is also $C_{i}^n$

For any basis k-vector $\alpha := e_{i_{1}}\land\dots \land e_{i_{k}}$ , there must be: $$\det(\alpha \land \star \alpha) = 1$$- This means that if we start with a "unit volume", wedging with its hudge star must also give a unit, positively-oriented unit volume.

![[Screenshot from 2023-03-20 15-00-09.png]]


## Important properties of Wedge product:

For a k-vector $\alpha$, l-vector $\beta$ and m-vector $\gamma$, we have

- Antisymmetry: $\alpha \land \beta = (-1)^{kl} \beta \land \alpha$
- Associativity: $\alpha \land (\beta \land \gamma) = (\alpha \land \beta)\land \gamma$

In the special case where $\beta$ and $\gamma$ have the same degree, we have

- Distributivity: $\alpha \land (\beta+\gamma) = \alpha \land \beta + \alpha \land \gamma$

