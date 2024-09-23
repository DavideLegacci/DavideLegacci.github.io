---
tags: game-theory
---

A key property of Nash equilibria in normal form games is that all players are indifferent among all of their supported choices.

# Slope points and Nash equilibria folk results

$$
\newcommand{\game}{\Gamma}
\newcommand{\players}{\mathcal{N}}
\newcommand{\play}{i}
\newcommand{\pures}{\mathcal{A}}
\newcommand{\pure}{\alpha}
\newcommand{\purealt}{\beta}
\newcommand{\pay}{u}
\newcommand{\others}{-i}
\newcommand{\strat}{x}
\newcommand{\strats}{\mathcal{X}}
\newcommand{\from}{:}
\newcommand{\R}{\mathbb{R}}
\newcommand{\findex}{\play \pure_{\play}}
\newcommand{\supp}{\text{supp}}
\newcommand{\BR}{\text{BR}}
$$
Let $\game = \game(\players, \pures, \pay)$ be a finite normal form game with players $\players$, pure profiles $\pures$ and payoff function $u$, and let $\strats$ denote the mixed strategy space.

For any player $\play$, fixed a choice $\strat_{\others}$ from the opponents, the payoff function $\pay_\play(\cdot, \strat_{\others}) \from \strats_\play \to \R$ is the linear, real-valued function on $\strats_i$ given by $\pay_\play(\strat_\play, \strat_{\others}) = \sum_{\pure_\play \in \pures_\play} \strat_{\findex} \pay_\play(\pure_\play, \strat_\others)$. 

> **Definition**
> The set of **best replies** to any $\strat_{\others} \in \strats_{\others}$ is 
> 
> $$ \BR_\play(\strat_{\others}) := \arg\max_{\strat_i \in \strats_i}\pay(\strat_\play, \strat_{\others}) \subseteq \strats_\play $$

By linearity of $\pay_{\play}(\cdot, \strat_{\others})$, the set of best replies to any $\strat_{\others}$ is a non-empty union of faces of $\strats_{\play}$, containing a vertex of $\strats_{\play}$ at least and the whole $\strats_{\play}$ at most.

> **Definition**
> A mixed strategy $\strat \in \strats$ is called **slope strategy** if each player $\play$ is indifferent among all of their choices, give that the others play $\strat_{\others}$:
> 
> $$\pay_\play(\pure_{\play}, \strat_{\others}) = \pay_\play(\purealt_{\play}, \strat_{\others}) \quad \text{for all } \play \in \players, \pure_{\play}, \purealt_{\play} \in \pures_\play $$

> **Definition**
> A mixed strategy $\strat \in \strats$ is called **slope-support** if if each player $\play$ is indifferent among all of their **available** choices, give that the others play $\strat_{\others}$:
> $$\pay_\play(\pure_{\play}, \strat_{\others}) = \pay_\play(\purealt_{\play}, \strat_{\others}) \quad \text{for all } \play \in \players, \pure_{\play}, \purealt_{\play} \in \supp_{\play}(\strat_\play) \subseteq \pures_{\play} $$

> **Definition**
> A mixed strategy $\strat \in \strats$ is called **Nash equilibrium** if it is a best reply to itself, in the sense that
> 
> $$ \strat_{\play} \in \BR_{\play}(\strat_{\others}) \quad \text{for all } \play \in \players $$
> A Nash equilibrium is **strict** if
>  $$ \{\strat_{\play}\} = \BR_{\play}(\strat_{\others}) \quad \text{for all } \play \in \players $$

> **Folk result on Nash equilibria and slope strategies**
> 1. A slope strategy is a Nash equilibrium
> 2. A Nash equilibrium is a slope-support strategy
> 3. A fully supported Nash equilibrium is a slope strategy.


**Proof**
For 1. Let $\strat$ be a slope strategy. Then for each player $\BR_{\play}(\strat_\others)$ is the whole $\strats_\play$, that contains in particular $\strat_\play$.

For 2. Since $\strat$ is Nash $\strat_\play \in \BR_\play(\strat_{\others})$, so by linearity $\BR_\play(\strat_{\others})$ contains the whole face of $\strats_\play$ that contains $\strat_i$,  for each player $\play$. In particular, it contains all of its vertices, that are precisely the pure strategies supported by $\strat_i$.

Point 3. is a direct consequence of 1. and 2. 