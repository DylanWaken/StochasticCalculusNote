----
A parameterized curve is a function that maps a real value between a specific interval into a point of some finite high dimensional space. This note uses 2D plane as an example, and the parameterized curve can be defined as:
$$\gamma : \mathbb{R} \to \mathbb{R}^2 , \gamma(s) = \begin{bmatrix}
\gamma_{x}(s) \\
\gamma_{y}(s)
\end{bmatrix}, s\in[0,L]$$
- Note the function is assumed to be smooth and differntiable

A **Discrete curve** is a piecewise linear parameterized curve, its defined by a sequence if verticies: $$\gamma_{0},\gamma_{1},\dots,\gamma_{n}, \gamma_{i} = \gamma(s_{i})$$
That are connected through straight line segments.

At each point, the parameterized curve has a **Unit Tangent** vector. This vector is defined by the derivative of the mapping function devided by the normalizing constant:
$$T(s):= \frac{d}{ds}\gamma(s) /\left\lvert  \frac{d}{ds} \gamma(s)  \right\rvert $$
- There is an assumption that the curve derivative is always non-zero 

If the curve have its derivative at every point to have exactly the norm of 1, then the curve is defined as an **arc-length parameterized** curve, with the unit tangent being:
$$T(s) := \frac{d}{ds} \gamma(s)$$
The normal to the curve is a vector that is always perpendicular to the tangent vector. The **unit normal** can be expressed as a quarter-rotation $\mathcal{J}$ of the unit tangent in counter clockwise direction, as:
$$N(s) := \mathcal{J}T(s)$$
- Note: in a 2d co-domain this can be done by $\mathcal{J}: [x,y] \to[-y,x]$

Note: the normal can be also defined as:
$$N(s) = \frac{T'(s)}{|T'(s)|}$$

![[Screenshot from 2023-03-04 10-07-13.png]]

The traditional definition of the curvature is given as:
$$\kappa(s) = |\frac{T'(s)}{\gamma'(s)}|$$
The Curvature is defined as **rate of change of the tangent in the normal direction** (speed of "vector rotation."). This is defined as (inner product of normal and change in tangent):  
$$\kappa (s) := \left\langle  N(s), \frac{d}{ds} T(s) \right\rangle$$
This can be also written as (for arc-length prameterized curves):
$$\kappa (s) := \left\langle  N(s), \frac{d^2}{ds^2} \gamma(s) \right\rangle$$
The reason for the inner product with the normal is that, it preserves the directional information of a curvature. (A signed quantity)
$$\kappa(s) := \left\langle  \mathcal{J} \frac{d}{ds}\gamma , \frac{d^2}{ds^2} \gamma  \right\rangle $$
## Discrete Curvature

Problem: using definition of curvature involve derivatives would give either zero or infinity on discrete defined curves:

![[Screenshot from 2023-03-04 10-24-32.png]]

Main Objectives:

- Satisfies sine if tge sane orioertues or theorems as smooth curvature
- convergence to smooth cervature as we refine curves
- efficient computation
- ...
#### 1: Turning angle.

![[Screenshot from 2023-03-04 10-20-57.png]]

1) Turning angle: the curvature is the **rate of change of the tangent in the normal direction**. This can be represented also as the change fo the angle between the unit tangent and the horizontal.
$$\kappa(s) =\frac{d}{ds}\phi(s)$$
- where $\phi$ is the angle between unit tangent and x axis

This operation cannot directly evaluate curvature. But the **integral** of this definition gives the difference in the angles between two given point on a curve, as:
$$\int _{a}^b \kappa (s)\, ds =\int _{a}^b \frac{d}{ds} \phi(s)\, ds =\phi(b)-\phi(a)$$

This definition is the total turning angle between the two points of sample.

This value can be evaluate on discrete curves (total curvature over segments).

![[Screenshot from 2023-03-04 10-28-02.png]]

#### 2: Length variation

Consider an arbitrary change in a parameterized curve $\gamma$ given by function $\eta :[0,L]\to \mathbb{R}^2$ where $\eta(0)=\eta(L)-0$. Due to the linearity of functions, this operation is defined as:
$$\gamma + \epsilon \eta$$
The curve length after the modification can be represented as:
$$L_{0}=\int _{0}^L |\gamma+\epsilon \eta|\, ds $$
the change in this quantity with respect to $\epsilon$ can be written as
$$\frac{dL_{0}}{d\epsilon} |_{\epsilon =0} = - \int _{0}^L \langle \eta(s), \kappa(s)N(s) \rangle \, ds $$
- Which is the product of variation times curvature and normal

To maximize the increase in the curve length, we need to align the direction of $\eta(s)$ and $\kappa(s)N(s)$. Which also stands for the equality as:
$$\nabla _{\epsilon} L_{0} = -\kappa(s)N(s) $$

![[Screenshot from 2023-03-04 11-36-24.png]]

For a specific line segment defined between $a,b$ and length $l=|b-a|$, the fastest increase in the length of the line is to directly extend in the direction of the line, which is given as: 
$$\nabla_{b}l = \frac{b-a}{l}$$
To find the compound curve made up of line segment, the same method can be used as the combination of gradients:
$$\nabla _{\gamma_{i}}L = 2 \sin\left( \frac{\theta_{i}}{2} \right) N_{i}, N_{i}= \frac{{u_{i}+ v_{i}}}{|u_{i} + v_{i}|}$$

Because of the correlation we derive above about the relationship between curvature and change in length, we can represent this quantity above as:
$$\kappa _{i} ^B N_{i} = 2 \sin\left( \frac{\theta_{i}}{2} \right) N_{i}, k_{i}^B = 2 \sin\left( \frac{\theta_{i}}{2} \right)$$
#### 3: Steiner's Formula (Discrete Normal Offset)

![[Screenshot from 2023-03-04 11-49-34.png]]

**Steiner's formula** referres to the relationship that if we move at a constant speed in the normal direction of the curve, then the change in length is proportional to curvature:
$$L_{0}(\eta+\epsilon N)=L_{0}(\eta)-\epsilon \int _{0} ^L \kappa(s)\, ds $$
The intuition behind this formula is that, the changeof length in curved area will be more significant than the flat area (as shown in the graph)

In discrete settings, the line segments would get disjointed if we exten them in the normal direction. To fix that, 3 connection methods (circular path, straight line, intersection of original lines extended) are introduced with 3 kinds of curvature definitions:

![[Screenshot from 2023-03-04 12-00-34.png]]

Where the original formulas are derived as:
$$\begin{align}
&L_{0}^{(A)}= L_{0}(\gamma) - \epsilon \sum_{i} \theta_{i} \\
&L_{0}^{(B)}= L_{0}(\gamma) - \epsilon \sum_{i} 2 \sin \left( \frac{\theta_{i}}{2} \right) \\ 
&L_{0}^{(C)}= L_{0}(\gamma) - \epsilon \sum_{i} 2 \tan \left( \frac{\theta_{i}}{2} \right) \\
\end{align}$$
Given the proportional relationship in Steiner's formula, the curvature definition is shown in the graphs.

#### 4: Osculating Circle

![[Screenshot from 2023-03-04 12-07-07.png]]

The Osculating circle is defined as the maximal circle that was "Tangent" to the curve, which means by approaching a specific point from both directions, the circle that these three points forms.

The definition of curvature given osculating circle is given as:
$$\kappa(s) = \frac{1}{r(s)}$$
![[Screenshot from 2023-03-04 12-11-01.png]]

Under the discrete settings, the same idea of two points approaching is agian used, and the discrete curvature is defined as:
$$k_{i}^D := \frac{1}{r_{i}} = 2 \frac{\sin(\theta_{i})}{w_{i}}$$
## Example: Curvature Flow

Curvature flow is the method that smooth out a noisy curve using curvature values

![[Screenshot from 2023-03-04 12-26-13.png]]

An example is the **curve shortening flow**, where we move a curve in the normal direction with the speed proportional the the curvature. 
$$\frac{d}{dt}\gamma(s,t) = \kappa(s,t) N (s,t)$$
This operation have the following properties:

- TOTAL: the total curvature remains constant throughout the flow
- DRIFT: the center of mass does not drift from the origin
- ROUND: Up to rescaling, the flow is stationary for circular curves.

Under discrete settings, the operation becames the movement of each vertex in the direction of the discrete curvature normal with speed defined by curvature:
$$\gamma_{i} ^{t+1} = \gamma_{i} ^t + \tau \kappa_{i} N _{i}$$
Note. our definitions of discrete curvatures cannot satisfies all 3 conditions above. In fact, each definition only captures a part of the story:

![[Screenshot from 2023-03-04 12-29-06.png]]

This is called no free launch theorem.

