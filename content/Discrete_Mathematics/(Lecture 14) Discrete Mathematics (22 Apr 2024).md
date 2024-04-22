---
title: Lecture 14
date: 22 Apr 2024
---
# Zero-sum Games
- These are games where the payoffs to the players are negative to each other.
- Games where the payoffs to Row player (Player A) are all non-negative

Payoff Matrix for just Player A:
$$
\begin{pmatrix}2 & 4\\3&1\end{pmatrix}
$$
**We need to find a mixed strategy**

For Player A, let $\bar p$ for the vector of probabilities for each action in a mixed strategy
$$
eg.\,\,\,\,\,\bar p=\begin{pmatrix}p_1\\p_2\end{pmatrix}=\begin{pmatrix}\text{Prob of playing action 1}\\\text{Prob of playing action 2}\end{pmatrix}\,\text{ for Player A}
$$
For Player B, let $\bar q$ be the vector of probabilities for each action in a mixed strategy
$$
\bar q=\begin{pmatrix}q_1\\q_2\end{pmatrix}=\begin{pmatrix}\text{Prob of playing action 1}\\\text{Prob of playing action 2}\end{pmatrix}\,\text{ for Player B}
$$
In general, vectors $p$ and $q$ could be any length.

Let $\bar 1$ represent a vector of 1s $\begin{pmatrix}1\\1\\1\\\vdots\\1\end{pmatrix}$
In particular, where we have two actions each $\bar 1=\begin{pmatrix}1\\1\end{pmatrix}$

What is the expected payoff to Player A?
$$
\text{Payoff Matrix }\begin{pmatrix}2&4\\3&1\end{pmatrix}=\bar R
$$
Probability that I play Action 1 at the same time as Player B plays action 1
$$
=p_1\times q_1
$$
Probability that I play Action 1 at the same time as Player B plays action 2
$$
=p_1q_2
$$
and so on.

$$
\text{The Expected Payoff to me (Player A)}=p_1\,q_1\times 2+p_1\,q_2\times 4+p_2\,q_1\times 3+p_2\,q_2\times 1
$$

$$
\begin{pmatrix}p_1&p_2\end{pmatrix}\begin{pmatrix}2&4\\3&1\end{pmatrix}\begin{pmatrix}q_1\\q_2\end{pmatrix}=\begin{pmatrix}p_1&p_2\end{pmatrix}\begin{pmatrix}2q_1+4q_2\\3q_1+q_2\end{pmatrix}=2p_1\,q_1+4p_1\,q_2+3p_2\,q_1+p_2\,q_2
$$
So the expected payoff to Player A is $\bar p^T\,\bar R\,\bar q$

If I'm player A, then I want to make this as big as possible, but I know that Player B is trying to make it as small as possible.

Let $v$ be the value of the game $=\bar p^T\,\bar R\,\bar q$ where we've all picked our $\bar p$ and $\bar q$ to be as good as possible to ourselves.

If I tell Player B my $\bar p$, they can't make things worse for me than $v$.

$$
\begin{pmatrix}p_1&p_2\end{pmatrix}\begin{pmatrix}2&4\\3&1\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}p_1&p_2\end{pmatrix}\begin{pmatrix}2\\3\end{pmatrix}=2p_1+3p_2\ge v
$$
Similarly
$$
\begin{pmatrix}p_1&p_2\end{pmatrix}\begin{pmatrix}2&4\\3&1\end{pmatrix}\begin{pmatrix}0\\1\end{pmatrix}=\begin{pmatrix}p_1&p_2\end{pmatrix}\begin{pmatrix}4\\1\end{pmatrix}=4p_1+p_2\ge v
$$
This has essentially turned into an optimization problem for Player A.

**Let us now look at the problem now from the point of view of Player B**

If Player B tells me their $\bar q$, I can't make things better for myself than $v$
$$
\begin{pmatrix}1&0\end{pmatrix}\begin{pmatrix}2&4\\3&1\end{pmatrix}\begin{pmatrix}q_1\\q_2\end{pmatrix}=\begin{pmatrix}2&4\end{pmatrix}\begin{pmatrix}q_1\\q_2\end{pmatrix}=2q_1+4q_2\le v
$$
$$
\begin{pmatrix}0&1\end{pmatrix}\begin{pmatrix}2&4\\3&1\end{pmatrix}\begin{pmatrix}q_1\\q_2\end{pmatrix}=\begin{pmatrix}3&1\end{pmatrix}\begin{pmatrix}q_1\\q_2\end{pmatrix}=3q_1+q_2\le v
$$
Player B wants to pick $q_1,\, q_2$ to make $v$ as small as possible
$$
\begin{array}{c}q_1+q_2=1\\q_1\ge 0\,\,\, q_2\ge 0\end{array}
$$
Since Player B wants to make $v$ as small as possible, she wants to make $\frac 1 v$ as big as possible. So the problem is
$$
\text{Maximise }\,\,\, y_1+y_2\,\,\,\left(=\frac 1 v\right) = \bar 1\cdot \bar y
$$
subject to constraints $y_1\ge 0$ and $y_2\ge 0$
$$
\begin{array}{c}2y_1+4y_2\le 1\\3y_1+y_2\le 1\end{array}
$$
$$
\boxed{\text{In general: Maximize }\bar 1\cdot \bar y\text{ subject to }\bar y\ge 0\text{ and }\bar R\bar y\le \bar 1}
$$
**Interpretation**
$$
\bar 1\cdot \bar y=\frac 1 v
$$
where $v$ is the expected payoff to Player A at optimal solution
$$
\bar y=\frac{1}v\times \bar q
$$
the probabilities of Player B choosing each action.
### Simplex method 
It is used for solving problem where I'm picking $\bar x$, maximizing $\bar c\cdot \bar x$

subject to constraints $\bar x\ge 0$ (element wise)
$$
\bar A\bar x\le \bar b\,\,\,\,\,\,\,\text{(element wise)}
$$
**Next bit of magic**
Let $y_1=\frac{q_1}{v}$ and $y_2=\frac{q_2}{v}$

$$
2q_1+4q_2\le v\implies \begin{array}{c}2\frac{q_1}{v}+4\frac{q_2}{v}\le 1\\\therefore 2y_1+4y_2\le 1\end{array}
$$
Similarly I get $3y_1+y_2\le 1$ from second constraint
$$
q_1+q_2=1\implies \frac{q_1}{v}+\frac{q_2}v=\frac 1 v=y_1+y_2=\frac 1 v
$$
In the Simplex method, it is all row operations, and it is all about thinking of rearranging $\bar A\bar x=\bar b$
$$
\begin{array}{c}2y_1+4y_2\le 1\\ 3y_1+y_2\le 1\end{array}\,\,\,\,\,\,\text{ with }y_1,y_2\le 0
$$
*Slack variable:* how much slack in the inequalities
$$
\begin{array}{c}2y_1&+4y_2&+S_1&&=1\\ 3y_1&+y_2&&+S_2&=1\end{array}\text{ with }\begin{array}{c}y_1,y_2\ge 0\\ s_1,s_2\ge 0\end{array}
$$
Inequalities are equivalent to the equation with extra condition $s_1,\, s_2\ge 0$
$$
\begin{array}{c}2y_1&+4y_2&+S_1&&&=1\\ 3y_1&+y_2&&+S_2&&=1\\-y_1&+-y_2&&&+\frac 1 v&=0\end{array}
$$
$$
\begin{pmatrix}2&4&1&0&0\\3&1&0&1&0\\-1&-1&0&0&1\end{pmatrix}\begin{pmatrix}y_1\\y_2\\s_1\\s_2\\\frac{1}v\end{pmatrix}=\begin{pmatrix}1\\1\\0\end{pmatrix}\,\,\,\text{with restriction that everything is +ve }\left(y_1,y_2,s_1,s_2,\frac 1 v\right)
$$
For any particular setup (i.e. tableau)

We can read off one possible solution very easily because part of our matrix looks like the identity.

A possible solution is to identify the elements with an identity column with the values of the right-hand side (RHS) and set everything else to zero.

$$
\begin{pmatrix}2&4&1&0&0\\3&1&0&1&0\\-1&-1&0&0&0\end{pmatrix}\begin{pmatrix}1\\1\\1\\1\\1\end{pmatrix}=\begin{pmatrix}1\\1\\0\end{pmatrix}\,\,\,\,\,\,\,\,\begin{array}{c}s_1=1\\s_2=1\\\frac{1}v=0\\y_1,y_2=0\end{array}
$$

___
**NOTE**
Since probabilities have to add up to 1, I know that $p_1+p_2=1$
We can write that as
$$
\bar 1\cdot\bar p=1
$$
$$
\begin{pmatrix}1&1\end{pmatrix}\begin{pmatrix}p_1\\p_2\end{pmatrix}=p_1+p_2=1
$$
Also,
$$
\bar 1\cdot \bar q=1
$$
___


