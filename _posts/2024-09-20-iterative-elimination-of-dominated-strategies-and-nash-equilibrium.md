---
tag: game-theory
---

In a finite game in normal form, if iterative elimination of weakly dominated strategies leads to a unique pure actions profile, then such action profile is a Nash equilibrium. 

# Iterative elimination of dominated strategies and Nash equilibrium

I had a hard time finding a complete proof of this well-known result: 

> If iterative domination of weakly dominated strategies leads to a singleton $a \in \mathcal{A}$, then $a$ is a Nash equilibrium.

The best I found is this great [handout on Itereated Elimination and Nash Equilibria](https://homepages.math.uic.edu/~marker/stat473-S16/IESDS.pdf) on the webpage of [David Marker](https://homepages.math.uic.edu/~marker/stat473-S16/) for the two-player case; here is the generalization to the $N$-player case.

Let $\Gamma = \Gamma(N, A, u)$. Let IEWDS mean [Iterative Elimination of Weakly Dominated Strategies](https://www.youtube.com/watch?v=E9IBWofIglc). Let $a^*$ be a IEWDS solution, meaning that IEWDS leads to the **unique** strategy profile $a^*$. Then $a^*$ is Nash equilibrium for $\Gamma$.

Let's stress that IEWDS leads to a **unique** outcome. If this is not the case, whatever remains after IEWDS, or even IWSDS (iterated elimination of strictly dominated strategies) needs not be a Nash equilibrium.

Recall that $a^*$ is a Nash equilibrium if it is a self best response, in the sense that

$$
a^*_i \in \text{BR}_i(a^*_{-i}) \quad \text{for all } i \in N
$$
or equivalently

$$
u_i(a^*_i, a^*_{-i}) \geq u_i(a_i, a^*_{-i})  \quad \text{for all } i \in N, a_i \in A_i.
$$
Reason by contradiction. Let $a^*$ be a IEWDS solution, and assume $a^*$ is not Nash. Then for some player $i$ there exist actions that perform better than $a^*_i$ against $a^*_{-i}$. Let $\tilde{A_i}$ be the set of these actions, that is

  $$
\tilde{A}_i =
\{ a_i \in A_i: u_i(a_i, a^*_{-i}) > u_i(a^*_i, a^*_{-i}) \}
$$
Clearly $a^*_i \notin \tilde{A}_i$, and by assumption $\tilde{A}_i \neq \emptyset$.

Since $a^*$ is the **unique** solution of IEWDS, every action of every player other than the one in $a^*$ must be eliminated at some point. In particular, every $a_i \in \tilde{A}_i$ must be eliminated at some stage. So for any $a_i \in \tilde{A}_i$ there exists a stage of the game in which $a_i$ is weakly dominated, that is there exists some $a_i' \in A_i$ still in the game such that

$$
u_i(a_i', b_{-i}) \geq u_i(a_i, b_{-i})
$$
for all $\beta_{-i}$ still in the game at that stage. In particular this must be true for $a^*_{-i}$ (which is never eliminated), so
$$
u_i(a_i', a^*_{-i}) \geq u_i(a_i, a^*_{-i}) > u_i(a^*_i, a^*_{-i})
$$
since $a_i \in \tilde{A}_i$. But then also $a'_i \in \tilde{A}_i$, so $a'_i$ must itself be eliminated at some later stage of the game. This procedure proceeds ad perpetuum, which is a contradiction (since the elimination procedure must terminate after finitely many steps to give $a^*$).
