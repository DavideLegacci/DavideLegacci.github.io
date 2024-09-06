# Understanding Gradients: From Geometry to Dynamics

*By Davide Legacci, November 8, 2021*

Gradients are an essential tool in mathematics, playing a crucial role in fields ranging from geometry to physics. 

In this post, we’ll explore some key facts about gradients, including their geometric interpretation and their connection to Lyapunov functions in dynamical systems.

## Directional derivative
Before diving into the definition of gradients on Riemannian manifolds, it is useful to recall the concept of **directional derivative**. Let then $M$ be a smooth manifold, $f: M \to \mathbb{R}$ a smooth function, and $X$ a vector field on $M$. The **directional derivative** of $f$ along $X$ is the smooth function

$$
Xf = df (X) = \sum_{i = 1}^n X^i \,  \partial_i{f} \tag{directional derivative}
$$

where the last expression holds only in a local chart.

>In the term $Xf$, the vector field $X$ is seen as a derivation over the space of smooth functions; in the term $df(X)$, the vector field $X$ is acted upon by the differential of $f$, which is a $1$-form on $M$, via the canonical dual pairing.

## Definition of gradient
Consider a smooth manifold $M$ with a Riemannian metric $g$, and let $f: M \to \mathbb{R}$ be a smooth function. The **gradient of $f$**, denoted by $\nabla{f}$, is the unique vector field on $M$ such that

$$
g(\nabla{f}, Y) = df ( Y) \tag{gradient}
$$

for all vector fields $Y$ on $M$.

## Gradients are Normal to Level Sets

Given a smooth manifold $M$ with a Riemannian metric $g$, let $f : M \to \mathbb{R}$ be a smooth submersion. The level set of $f$, denoted as $\Sigma = \{f = \text{const}\}$, is a smooth submanifold of $M$. This setup allows us to think of $\Sigma$ as a surface within the manifold where the value of $f$ is constant.

The first geometric fact is that the gradient of $f$ is **normal** to the level set $\Sigma$. But what does that mean?

The tangent space $T_p \Sigma$ to the submanifold at a point $p \in \Sigma$ consists of all possible directions you could move along the surface $\Sigma$ from $p$. Mathematically, it’s the kernel of the differential of $f$ at $p$:

$$
T_p \Sigma = \ker d f_p \tag{1}
$$

The remarkable thing is that this gradient vector is perpendicular (or **normal**) to the level set $\Sigma$. Indeed,

$$
g_p(\nabla f_p, u) = d f_p ( u) = 0 \quad \text{for all } u \in T_p \Sigma \tag{2}
$$

This relationship shows that no matter which direction you move along the surface $\Sigma$, the gradient of $f$ remains orthogonal to that motion.

## Direction of Maximum Change: Following the Gradient

One of the most important properties of the gradient of a function is that it points in the direction of the **maximum rate of change** of the function $\textendash$ not only in Euclidean spaces but also on more general manifolds.

To formalize this, let

$$
U = \{ u \in \tau(M) : \|u\| = 1 \} \tag{3}
$$

be the space of **directions**, namely unit vector fields.

If you’re standing at a point $p \in M$, you might wonder which direction will increase $f$ the fastest. In other words, for any point $p \in M$, it makes sense to ask which is the direction that maximises the map $u \mapsto (uf)_p \in \mathbb{R}$, where $(uf)_p$ is the directional derivative of $f$ along $u$ at $p$. This boils down to solving:

$$
\arg \max_{u \in U} (u f)_p \quad \text{for any } p \in M \tag{5}
$$

==get rid of cosine argument==
Geometrically, the cosine of the angle between the gradient $\nabla f$ and a direction $u$ tells you how aligned they are:

$$
g_p(a, b) = \|a\| \|b\| \cos \theta \tag{6}
$$

If the cosine is 1 (i.e., $\theta = 0$), then $u$ and $\nabla f$ point in the same direction. Thus, the directional derivative is maximized when $u$ is parallel to the gradient $\nabla f$:

$$
\arg \max_{u \in U} (u f)_p =
\frac{\nabla f}{\|\nabla f\|}
\Big|_p \tag{8}
$$

This tells us that to experience the fastest increase in $f$, you should move in the direction of the gradient vector $\nabla f$.

## Gradients as Lyapunov Functions: Stability in Dynamical Systems

Gradients aren’t just geometric tools—they play a key role in understanding stability in dynamical systems. Consider a system defined by the following differential equation:

$$
\dot{x} = X(x), \quad X = \nabla f \tag{9}
$$

This describes a system where the velocity of the state $x$ is determined by the gradient of some potential function $f$. A natural question to ask is whether $f$ serves as a **Lyapunov function** for the system, which is a function that helps us analyze the stability of equilibrium points.

To check this, we compute the **Lie derivative** of $f$ along the vector field $X$:

$$
L_X f = X f = d f(X) = g(\nabla f, X) = g(X, X) \geq 0 \tag{10}
$$

The inequality tells us that the function $f$ is non-decreasing along the trajectories of the system, and equality holds at points where $X = 0$—these are the **equilibrium points**. In other words, $f$ is indeed a Lyapunov function, and the system tends to stabilize at points where the gradient vanishes.

## Conclusion: A Tool Across Fields

The gradient is a versatile mathematical tool, with applications spanning geometry and dynamics. Its geometric role in being normal to level sets helps us visualize change, while its dynamical role as a Lyapunov function guides us in analyzing stability. Whether you're studying manifolds or designing stable systems, understanding gradients is essential for navigating the complexities of mathematical landscapes.

Stay tuned for more insights into mathematical concepts and their applications in future blog posts!