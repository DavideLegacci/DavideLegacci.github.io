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

## Best of both worlds

[^rom]: S. Roman, S. Axler, and F. Gehring, _Advanced linear algebra_, 3rd ed. Springer, 2008.
[^kam]: K. Kamaraj and K. C. Sivakumar, “Moore-Penrose inverse in an indefinite inner product space,” _JAMC_, vol. 19, no. 1, pp. 297–310, Mar. 2005
[^alv]: F. Alvarez, J. Bolte, and O. Brahic, “Hessian Riemannian gradient flows in convex programming,” _SIAM J. Control Optim._, vol. 43, no. 2, pp. 477–501, Jan. 2004, doi: [10.1137/S0363012902419977](https://doi.org/10.1137/S0363012902419977).
