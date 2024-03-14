---
title: Lecture 9
date: 13 Mar 2024
---
$$
\begin{array}{c|c|c|c|c|c}&\text{Groupoid}&\text{Semigroup}&\text{Monoid}&\text{Group}&\text{Abelian Group}\\\hline\text{Closed}&✅&✅&✅&✅&✅\\\text{associative}&❌&✅&✅&✅&✅\\\text{Identity}&❌&❌&✅&✅&✅\\\text{Inverses}&❌&❌&❌&✅&✅\\\text{Commutative}&❌&❌&❌&❌&✅\end{array}
$$
____
**Definition of Ring**: A set $R$ and two binary operators $+$ and $\cdot$ forms a ring if:
$$
(R1)\,\,\,\,\,\,[R,+]\text{ forms an abelian group}
$$
$$
(R2)\,\,\,\,\,[R, \cdot]\text{ forms a monoid}
$$
$$
(R3)\,\,\,\,\,\,\text{multiplication is distributive over addition}
$$
This means that
$$
\begin{array}{c}a\cdot(b+c)=(a\cdot b)+(a\cdot c)\\ (b+c)\cdot a=(b\cdot a)+(c\cdot a)\end{array}
$$
## Example
Show that the integer $\mathbb{Z}$ forms a ring under usual addition and multiplication

**Sketch Proof**
$$
(R1)\,\,\,\,[\mathbb{Z},+]\text{ forms an abelian group}
$$
$$
(R2)\,\,\,\,[\mathbb{Z},\cdot]\text{ forms a monoid}
$$
$$
(R3) \cdot\text{ is distributive over }+
$$
From previous axioms, we know that all the above three statements can be proved.
___

Let's take a ring without identity 
$$
\text{rng }\,\,\,[R,\cdot]\text{ forms a semigroup}
$$
- If 1 exists (identity exists), we get a
$$
\text{ring (with identity)}\,\,\,\,[R,\cdot]\text{ forms a monoid}
$$
- By requiring inverses, we get
$$
\text{division ring}\,\,\,[R-\{0\},\cdot]\text{ forms a group}
$$

N.B. $[\mathbb{Z},\cdot]\text{ is not a group}$ 
$$
\begin{array}{c}2\cdot x=1\\ x=\frac 1 2\notin \mathbb{Z}\end{array}
$$
$\mathbb{Z}$ does not form a Division ring.

- If multiplication is commutative, we get a
$$
\text{commutative ring}
$$
- If a commutative ring has a ring with identity, and no zero divisors $(\forall\, a,b\in R)$, we get
$$
\text{Integral domain}
$$

Suppose to the contrary $\mathbb{Z}$ does contain zero divisors, $a$ and $b$
Then,
$$
a\cdot b=0\,\,\,\text{ but }a=0\text{ or }b=0
$$
So we get a contradiction. 

- And if we have an integral domain and a division ring, then we get a 
$$
\text{field}
$$
____
## Example
Consider the set of $2\times 2$ matrices
$$
\mathcal{F}=\begin{Bmatrix}\begin{pmatrix}1&0\\0&1\end{pmatrix},\begin{pmatrix}1&1\\1&0\end{pmatrix},\begin{pmatrix}0&1\\1&1\end{pmatrix},\begin{pmatrix}0&0\\0&0\end{pmatrix}\end{Bmatrix}
$$
under arithmetic in $\mathbb{Z}_2$. Is it a Field?

**Sketch Proof:**
$$
(F1)\,\,\,[F,+]\text{ form abelian group?}
$$
The above statement is closed, associative, identity, and is a self-inverse.
$$
(F2)\,\,\,\left[F-\begin{Bmatrix}\begin{pmatrix}0&0\\0&0\end{pmatrix}\end{Bmatrix},\cdot\right]\text{ form an abelian group?}
$$
We know that the above statement is associative, identity $\begin{pmatrix}1&0\\0&1\end{pmatrix}$
$$
\begin{array}{c|cc}&\begin{pmatrix}1&1\\1&0\end{pmatrix}&\begin{pmatrix}0&1\\1&1\end{pmatrix}\\\hline\begin{pmatrix}1&1\\1&0\end{pmatrix}&\begin{pmatrix}0&1\\1&1\end{pmatrix}&\begin{pmatrix}1&0\\0&1\end{pmatrix}\\\begin{pmatrix}0&1\\1&1\end{pmatrix}&\begin{pmatrix}1&0\\0&1\end{pmatrix}&\begin{pmatrix}1&1\\1&0\end{pmatrix}\end{array}
$$
$$
(F3)\,\,\,\,\text{ distributivity?}
$$
We know the above statement is true from the axioms.
____
$$
\phi:A\rightarrow B
$$
- $\phi \text{ is a homorphism if }\phi\text{ preserves all operators.}$
$$
\begin{array}{c}\phi(a_1+_A a_2)=\phi(a_1)+_B\phi(a_2)\\\phi(a_1\cdot_A a_2)=\phi(a_1)\cdot_B\phi(a_2)\end{array}
$$
- $\phi$ is then also injective $\rightarrow$ mono morphism
	- also surjective $\rightarrow$ epimorphism
	- also bijective $\rightarrow$ isomorphism

Homework: Show that
$$
\phi:\mathbb{Z}\rightarrow \mathbb{Z}_2
$$
$$
\text{odd}\mapsto 1
$$
$$
\text{even}\mapsto0
$$



