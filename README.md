# CPS485 Homework 3 — PAC Learnability

**Group draft**  
**Group members:** Rahsaun Jeffrey and [collaborator name]

## Problem 1

Let $H$ contain the classifier $h_T$ for every finite set $T$ of positive integers, including the empty set. Each $h_T$ predicts $1$ exactly on the integers in $T$. Is $H$ PAC-learnable?

## Proof

**The hypothesis class $H$ is not PAC-learnable because it has infinite VC dimension.**

Let $n$ be any positive integer and consider the set $S = \{1, 2, \ldots, n\}$. Choose any labeling $y: S \to \{0,1\}$ and define

$$
T = \{i \in S : y(i)=1\}.
$$

Because $T \subseteq S$, the set $T$ is finite, so $h_T$ belongs to $H$. For every $i \in S$, the classifier $h_T$ predicts $1$ exactly when $i \in T$, which is exactly when $y(i)=1$. Thus $h_T(i)=y(i)$ for every $i \in S$. This also covers the labeling that assigns $0$ to every point, since $H$ includes $h_{\varnothing}$.

Therefore $H$ realizes every labeling of $S$, so it shatters $S$. Since $n$ was arbitrary, $H$ can shatter sets of arbitrarily large finite size. Hence $\operatorname{VCdim}(H)=\infty$. By the fundamental theorem of statistical learning, a binary hypothesis class is distribution-free PAC-learnable only if it has finite VC dimension. Therefore $H$ is not PAC-learnable.
