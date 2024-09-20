---
tag: game-theory
---


In a finite game in normal form, if iterative elimination of weakly dominated strategies leads to a unique pure actions profile, then such action profile is a Nash equilibrium. 

# Iterative elimination of dominated strategies and Nash equilibrium

I had a hard time finding a complete proof of this well-known result: 

> If iterative domination of weakly dominated strategies leads to a singleton $a \in \mathcal{A}$, then $a$ is a Nash equilibrium.

The best I found is this great [handout on Itereated Elimination and Nash Equilibria](https://homepages.math.uic.edu/~marker/stat473-S16/IESDS.pdf) on the webpage of [David Marker](https://homepages.math.uic.edu/~marker/stat473-S16/) for the two-player case; here is the generalization to the $N$-player case.

Let $\Gamma = \Gamma(N, A, u)$. Let IEWDS mean [Iterative Elimination of Weakly Dominated Strategies](https://www.youtube.com/watch?v=E9IBWofIglc). Let $a^{\ast}$ be a IEWDS solution, meaning that IEWDS leads to the unique strategy profile $a^{\ast}$. Then $a^{\ast}$ is Nash equilibrium for $\Gamma$.

Let's stress that IEWDS leads to a unique outcome. If this is not the case, whatever remains after IEWDS, or even IWSDS (iterated elimination of strictly dominated strategies) needs not be a Nash equilibrium.

Recall that $a^{\ast}$ is a Nash equilibrium if it is a self best response, in the sense that

$$
a^{\ast}_{i} \in \text{BR}_{i}(a^{\ast}_{-i}) \quad \text{for all } i \in N
$$

or equivalently

$$
u_{i}(a^{\ast}_{i}, a^{\ast}_{-i}) \geq u_{i}(a_{i}, a^{\ast}_{-i})  \quad \text{for all } i \in N, a_{i} \in A_{i}.
$$

Reason by contradiction. Let $a^{\ast}$ be a IEWDS solution, and assume $a^{\ast}$ is not Nash. Then for some player $i$ there exist actions that perform better than \(a^{\ast}_{i}\) 

against $a^{\ast}_{-i}$. Let $\tilde{A_{i}}$ be the set of these actions, that is

$$
\tilde{A}_{i} =
\{ a_{i} \in A_{i}: u_{i}(a_{i}, a^{\ast}_{-i}) > u_{i}(a^{\ast}_{i}, a^{\ast}_{-i}) \}
$$

Clearly $a^{\ast}_{i} \notin \tilde{A}_{i}$, and by assumption $\tilde{A}_{i} \neq \emptyset$.

Since $a^{\ast}$ is the unique solution of IEWDS, every action of every player other than the one in $a^{\ast}$ must be eliminated at some point. In particular, every $a_{i} \in \tilde{A}_{i}$ must be eliminated at some stage. So for any $a_{i} \in \tilde{A}_{i}$ there exists a stage of the game in which $a_{i}$ is weakly dominated, that is there exists some $a_{i}' \in A_{i}$ still in the game such that

$$
u_{i}(a_{i}', b_{-i}) \geq u_{i}(a_{i}, b_{-i})
$$

for all $\beta_{-i}$ still in the game at that stage. In particular this must be true for $a^{\ast}_{-i}$ (which is never eliminated), so

$$
u_{i}(a_{i}', a^{\ast}_{-i}) \geq u_{i}(a_{i}, a^{\ast}_{-i}) > u_{i}(a^{\ast}_{i}, a^{\ast}_{-i})
$$

since $a_{i} \in \tilde{A}_{i}$. But then also $a'_{i} \in \tilde{A}_{i}$, so $a'_{i}$ must itself be eliminated at some later stage of the game. This procedure proceeds ad perpetuum, which is a contradiction (since the elimination procedure must terminate after finitely many steps to give $a^{\ast}$).

