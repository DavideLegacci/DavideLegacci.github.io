---
tags: geometry
---

Just some quick notes on orthogonal projections onto regular level sets.

# A quick note on orthogonal projections

- [[#The linear algebraic point of view|The linear algebraic point of view]]
	- [[#The linear algebraic point of view#Full-rank case|Full-rank case]]
	- [[#The linear algebraic point of view#Full-rank, surjective, Riemannian case|Full-rank, surjective, Riemannian case]]
- [[#The differential point of view|The differential point of view]]
- [[#Best of both worlds|Best of both worlds]]


$\newcommand{\R}{\mathbb{R}}$
$\newcommand{\from}{:}$
$\newcommand{\pin}[1]{\tilde{#1}}$
$\DeclareMathOperator{\im}{im}$
$\DeclareMathOperator{\grad}{grad}$
$\DeclareMathOperator{\id}{I}$
$\DeclareMathOperator{\dim}{dim}$

## The linear algebraic point of view

If $A: U \to V$ is a linear map between Euclidean spaces, there exist a powerful and simple way to build the orthogonal projections onto its kernel and onto its image: the [Moore–Penrose inverse](https://en.wikipedia.org/wiki/Moore%E2%80%93Penrose_inverse). Indeed there always exists[^rom] a linear map $\pin{A} \from V \to U$ characterized by
1. $\pin{A}A\pin{A} = \pin{A}$
2. $\pin{A}A$ and $A\pin{A}$ are self-adjoint.

If $A$ is invertible then $\pin{A} = A^{-1}$.

Note that $\pin{A}A \from U \to U$ and $A\pin{A} \from V \to V$ are endomorphisms. They are the maps we are interested in:

> $A\pin{A} \from V \to V$ is the orthogonal projection 
> - onto $\im{A\pin{A}} = \im{A} =\left(\ker{\pin{A}}\right)^{\perp}$
> - along $\ker{A\pin{A}} = \ker{\pin{A}} = \left(\im{A}\right)^{\perp}$

> $\pin{A}A \from U \to U$ is the orthogonal projection
>  
>  $$
>  \tag{1}
>  \text{onto }\im{\pin{A}{A}} = \im{\pin{A}} =\left(\ker{A}\right)^{\perp}
>  $$
>  
> along $\ker{\pin{A}{A}} = \ker{A} = \left(\im{\pin{A}}\right)^{\perp}$

### Full-rank case
The Moore-Penrose inverse can be computed in closed form, and this procedure is particularly simple in the case of **full-ranked** $A$. Let $\dim{U} = n$ and $\dim{V} = m$ with $A \from U \to V$, so $A \in \R^{m \times n}$.
- if $n = m$ ($A$ invertible), then $\pin{A} = A^{-1}$;
- if $n > m$ ($A$ surjective), then

$$
\tag{2}
\pin{A} = A^T\left( AA^T \right)^{-1};
$$

- if $n < m$ ($A$ injective), then $\pin{A} = \left(A^{T}A\right)^{-1}A^T$.


All these notions generalize neatly to generic (as opposed to Euclidean) inner product spaces;[^kam] at the moment I'm interested in the full-rank, surjective, non-Euclidean case.

### Full-rank, surjective, Riemannian case
Let $A \from U \to V$ be a full-rank linear map between vector spaces, with $n = \dim{U} > \dim{V} = m$ (so $A$ is surjective and not injective).

Equip $U$ be equipped with the Riemannian metric $g$. This means that $g$ is a smooth field of inner products, that is for each $x \in U$ we have an inner product $g_x: U \times U \to \R$.

For each $x \in U$ we want to build the orthogonal projection $P_x \from U \to U$ onto the kernel of $A$ with respect to the inner product $g_x$. This turns out to be[^kam][^alv]

$$
\tag{3}
P_x = \id - g_x^{-1}A^T \left( A g_x^{-1} A^T  \right)^{-1} A
$$

We don't prove this here, but just perform some consistency checks and develop an intuition of where this might come from.
- Since $P_x$ is the orthogonal projection onto $\ker{A}$, the operator after the minus sign must the be orthogonal projection onto $\left(\ker{A}\right)^{\perp}$;
- By Eq. $(1)$, in the Euclidean case $(g_x = \id)$ this is $\pin{A}A$;
- Indeed, by $(2)$ in the Euclidean full-rank surjective case we have $\pin{A} = A^T\left(AA^T\right)^{-1}$

Thus $(3)$ is the non-Euclidean generalisation of $(1)$ in the full-rank, surjective case $(2)$ ✅.

Dimensionally, a vector in $U$ has shape $n\times1$ (column vector), and $P_x$ must be $n \times n$. Indeed $g_x$ and $g_x^{-1}$ are $n \times n$, $A$ is $m \times n$, $A^T$ is $n \times m$, and all works out well. 


## The differential point of view
Different point of view now. Let $S$ be a submanifold[^lee] of a Riemannian manifold $(M,g)$. If $X$ is a vector field on $M$ then its orthogonal projection with respect to $g$ onto $S$ is the vector field $X_S$ on S given by

$$
X_S = X - \frac{g(X,n)}{g(n,n)} \, n
$$

where $n$ is any vector field in $M$ that is normal to $S$.

### Level sets of smooth submersions and gradients
If $F \from M \to N$ is a smooth submersion between smooth manifolds, that is a smooth function whose differential is surjective,[^regular] then its level sets $S_y = {x \in M: F(x) = y}$ are smooth submanifolds of $M$ of dimension $\dim{M} - \dim{N}$, for all $y \in N$.

If $N = \R$ then $S$ has codimension $1$, and the tangent space to $S$ at a point $x$ is the kernel of the differential of $F$, $T_{x}S = \ker{d_xF}$, so that the gradient of $F$ is a vector field in $M$ normal to $S$:

$$
g_x(\grad{F}_x, u) = d_xF\cdot{u} = 0 \quad \text{ for all } u \in T_{x}S.
$$

Thus if $X$ is a vector field in $(M,g)$, its  orthogonal projection $X_S$ onto the level set $S$ of a smooth submersion $F \from M \to \R$ is

$$
\tag{4}
X_S = X - \frac{g(X,\grad{F})}{g(\grad{F},\grad{F})} \, \grad{F}.
$$

## Best of both worlds
Let now $A \from M = \R^n \to \R$ be a full-rank linear surjection, and let $S = \ker{A}$ be its zero level set. In this case, Eq. $(4)$ should reduce to Eq. $(3)$.

In matrix form we have that $A \in \R^{1 \times n}$, and by linearity the differential of $A$ can be identified with $A$ itself, and thought of as a row vector: $d_xA \cong A: T_{x}\R^n \cong \R^n \to T_{Ax}\R \cong\R$. The gradient of $A$ at a point $x$ is the $n\times 1$ column vector 

$$\grad_{x}A = g_x^{-1} \left( d_{x}A \right) = g_{x}^{-1}A^T,
$$

where in the second term the $(2,0)$ tensor $g_{x}^{-1}$ acts on the $(0,1)$ tensor $d_x{A}$ by canonical duality pairing, and the last term is to be read as matrix equation; dimensions are consistent since $g_x^{-1}$ is $n \times n$ and $A^T$ is $n \times 1$.

By $(4)$ the orthogonal projection of a vector field $X$ in $M$ onto $S$ with respect to $g$ is

$$
\begin{split}
X_S
& = X - \frac{g(X,\grad{A})}{g(\grad{A},\grad{A})} \, \grad{A} \\
& =  X - \frac{AX}{Ag^{-1}A^T} \, g^{-1}A^T \\
\end{split}
$$

which is dimensionally consistent (the fraction is a scalar, and $X$ and $g^{-1}A^T$ are $n\times 1$), and is precisely Eq. $(3)$ in the case $m = 1$.




[^rom]: S. Roman, S. Axler, and F. Gehring, _Advanced linear algebra_, 3rd ed. Springer, 2008.
[^kam]: K. Kamaraj and K. C. Sivakumar, “Moore-Penrose inverse in an indefinite inner product space,” _JAMC_, vol. 19, no. 1, pp. 297–310, Mar. 2005
[^alv]: F. Alvarez, J. Bolte, and O. Brahic, “Hessian Riemannian gradient flows in convex programming,” _SIAM J. Control Optim._, vol. 43, no. 2, pp. 477–501, Jan. 2004, doi: [10.1137/S0363012902419977](https://doi.org/10.1137/S0363012902419977).
[^lee]: J. M. Lee, _Introduction to Smooth Manifolds_, 2nd ed. in Graduate Texts in Mathematics. Springer-Verlag New York, 2012.
[^regular]: This can be relaxed to *regular level sets* of smooth functions that are not necessarily submersions by requiring the level sets to not contain critical points; cf [An exercise on regular level sets](./2024-10-04-an-exercise-on-regular-level-sets.md).