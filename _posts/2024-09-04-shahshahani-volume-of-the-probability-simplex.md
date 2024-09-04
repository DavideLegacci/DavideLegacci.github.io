
Let's compute the volume of the probability simplex with respect to the Shahshahani metric.


# Riemanniann volume of the probability simplex under the Shahshahani metric

$\DeclareMathOperator{\Vol}{Vol}$
$\DeclareMathOperator{\d}{d\!}$
$\DeclareMathOperator{\J}{J\!}$


## Shashahani  metric on the simplex

In the following, greek indices take the values $\mu = 0, 1, \dots, n$,  and latin indices take the values $i = 1, \dots, n$.

In the positive hyperoctant $\mathbb{R}_{>0}^{n+1}$, the Shahshahani metric is $$g = g_{\mu\nu}\d{x}^{\mu}\otimes\d{x}^{\nu}$$ with
$$g_{\mu\nu}(x) = \frac{\delta_{\mu\nu}}{x_\mu}$$In matrix notation,
$$g_{\mu\nu}(x) = \text{diag}\left(\frac{1}{x_0},\frac{1}{x_1}, \dots, \frac{1}{x_n} \right)$$
Consider the relative interior of the $n$-dimensional probability simplex 

$$\mathring{\Delta}^n = \{x \in \mathbb{R}^{n+1}_{>0}: x_{\mu} >0, \sum_\mu x_{\mu} = 1\} \subset \mathbb{R}^{n+1}_{>0}$$


**Our goal is to compute the volume of $\mathring{\Delta}^n$ under the Shahshahani metric.**

$\mathring{\Delta}^n$ is a smooth manifold with global chart $$\phi: \mathring{\Delta}^n \to U \in \mathbb{R}^n$$$$\phi(x_0, x_1, \dots, x_n) = (s_1, \dots, s_n)$$
where $U$ is the open corner of cube

$$U = \{s \in \mathbb{R}^n: s_i >0, \sum_i s_i < 1\}$$The inverse chart is $$\psi = \phi^{-1}: U \to \mathring{\Delta}^n$$

$$\psi(s_1, \dots, s_n) = (x_0, x_1, \dots, x_n)$$ with $$x_0 = 1-\sum_js_j, \quad x_i = s_i$$

Let $\iota: \mathring{\Delta}^n \hookrightarrow \mathbb{R}^{n+1}_{>0}$ denote the inclusion. The volume of the open simplex under the Shahshahani metric is given by


$$
\Vol_{\text{Sha}}\mathring{\Delta}^n = \int_{\mathring{\Delta}^n} \omega_{\iota^*g}
$$

where $\omega$ is the Riemannian volume form.

Pull back the Shahshahani metric from the positive orthant to $U$ along $\iota \circ \psi: U \to \mathbb{R}^{n+1}_{>0}$:

$$
h := (\iota \circ \psi)^*g = h_{ij} \d{s}^i \otimes \d{s}^j
$$

After a quick calculation,

$$h_{ij}(s) = \frac{\delta_{ij}}{s_i} + \frac{1}{1-\sum_ks_k}$$

The determinant of this metric can be computed with the Matrix Determinant 

$$\det(A+u\otimes v) = (1+v\cdot A^{-1}u)\det{A}$$

and gives 

$$\det{h}(s) = \frac{1}{\left(1-\sum_is_i\right)\prod_js_j}$$

---


>**Determinant of pull-back metric**
In general the determinant of the pull-back metric isn't the same thing of the determinant of the ambient metric; this seems to be a special property of the Shahshahani metric.
As a counter example, consider the Euclidean 3-metric with determinant $1$, and the metric induced on the two-sphere

$$g = \begin{pmatrix}
1 & 0 \\
0 & \sin^2(\theta)
\end{pmatrix}$$

with determinant $\sin^2(\theta)$.

---

So the Sha. volume of the $n$-simplex is

$$
\begin{split}
\Vol_{\text{Sha}}\mathring{\Delta}^n &= \int_{\mathring{\Delta}^n} \omega_{\iota^*g} \\
& = \int_U\omega_h = \int_{s_1>0, \,  \dots, \,  s_n>0,\, \sum_is_1<1}\sqrt{\det{h}}\d{s}^1 \dots \d{s}^n \\
& = \int_{s_1:0}^1\int_{s_2:0}^{1-s_1}\cdots\int_{s_n:0}^{1-s_1-\cdots-s_{n-1}}\frac{1}{\sqrt{\left(1-\sum_is_i\right)\prod_js_j}} \d{s}^n \cdots \d{s}^{1} \\
& = \int_{s_1=0}^{\alpha_1}\frac{\d{s}^1}{\sqrt{s_1}} \int_{s_2=0}^{\alpha_2}\frac{\d{s}^2}{\sqrt{s_2}} \cdots \int_{s_{n-1}=0}^{\alpha_{n-1}}\frac{\d{s}^{n-1}}{\sqrt{s_{n-1}}}\int_{s_n=0}^{\alpha_n}\frac{\d{s}^n}{\sqrt{s_n(\alpha_n-s_n)}}
\end{split}
$$

with

$$\alpha_n = 1-s_1-\cdots-s_{n-1}$$

The integrals can be computed in closed form and shown to be finite for each value of $n$, for example

$$\Vol_{\text{Sha}}\mathring{\Delta}^1 = \pi$$

$$\Vol_{\text{Sha}}\mathring{\Delta}^2 = 2\pi$$

$$\Vol_{\text{Sha}}\mathring{\Delta}^3 = \pi^2$$
## Akin's sphere trick

A smarter approach gives the sought-after volume in closed form for any value of $n$. The $n$-simplex endowed with the Shahshahani metric is isometric to the portion of the radius-2 $n$-sphere in the positive hyperoctant endowed with the Euclidean metric (Akin, *The Geometry of Population Genetics*, p.39) via

$$
y = 2\sqrt{x}
$$

Since isometries preserve volumes, the Shahshahani volume of the $n$-simplex is the Euclidean surface of the portion of the $n$-hypersphere of radius 2 in the positive hyperoctant, that is 

$$\Vol_{\text{Sha}}\mathring{\Delta}^n =\frac{\pi^{\frac{n+1}{2}}}{\Gamma(\frac{n+1}{2})}$$

where $\Gamma$ is the [gamma function](https://en.wikipedia.org/wiki/Gamma_function).

### Isometries preserve volumes
Given an isometry $F: M \to N$ between Riemannian manifolds, with $g$ metric on $N$, we have that

$$\Vol_g{N} = \Vol_{F^*g}M$$

**Proof sketch**

$$
\begin{split}
\Vol_g{N} & = \int_N \omega_g \\
& = \int_{F^{-1}N}F^*\omega_g \\
& = \int_M F^* \left( \sqrt{\det{g}}\d{y}^I \right)\\
& = \int_M(F^*\sqrt{\det{g}})(F^*\d{y}^I) \\
& = \int_M(F^*\sqrt{\det{g}})(\det{\J{F}})\d{x}^I \\
\\
\Vol_{F^*g}{M} & = \int_M \omega_{F^*g} \\ & = \int_{M}\sqrt{\det{F^*g}}\d{x}^I
\end{split}
$$

$$\sqrt{\det{F^*g}} = (\sqrt{\det{g}}\circ F)(\det{\J{F}})$$

which concludes the proof.
