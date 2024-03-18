---
title: Lecture 10
date: 18 Mar 2024
---
# Polynomial Rings
The general definition of a polynomial
$$
f(x)=a_nx^n+a_{n-1}x^{n-1}+\dots+a_1x+a_0
$$
Polynomials forms a ring, and can be written as 
$$
f(x)=\sum_{i=0}^n a_ix^{i}
$$
where $a_i\in R$ then $R[x]$ is the polynomial ring over R with *indeterminate* $x$.
- Indeterminate means $x$ need not be an element of the ring

$a_i$ are called coefficients
$a_n$ where $n$ is the greatest positive power of $x\rightarrow$ *leading coefficient*

The degree $\text{deg}(f(x))=n$, then $a_n=1$ is known as a *monic polynomial*.
$$
\text{deg}=2\begin{cases}2x^2-4\\ a_2=2\,\,\,\,\,\,\,a_1=0\,\,\,\,\,\,\,a_0=-4\\ x^2-4\end{cases}
$$
when $a_n,\dots,a_1=0$, but $a_0\ne 0$, then it is known as a *constant*.

We can see that this forms a ring.
## Polynomial Addition
Lets say we have two polynomials $f(x)$ and $g(x)$ defined as below,
$$
f(x)=a_0+a_1x+\dots+a_nx^n
$$
$$
g(x)=b_0+b_1x+\dots+b_nx^n
$$
Adding the two polynomials
$$
f(x)+g(x)=c_0+c_1x+c_2x^2+\dots+c_nx^n\,\,\,\,\,\,\,\,\text{where }c_i=a_i+_Rb_i
$$
This is like addition under the ring.
## Polynomial Multiplication
Multiplication of the two polynomials
$$
(f\cdot g)(x)=f(x)\cdot g(x)=c_0+c_1x+c_2x^2+\dots+c_nx^n
$$
where
$$
c_i=\sum_{k=0}^i a_kb_{i-k}=a_0\cdot_Rb_i+_P a_1\cdot_Rb_{i-1}+\dots+_R a_i\cdot_R b_o
$$

### Example
Suppose we have
$$
p(x)=x^3-3x+2\,\,\,\,\,\,\,\text{ and }\,\,\,\,\,\, q(x)=3x^2-6x+5
$$
The multiplication of the two polynomials is 
$$
\begin{split}(pq)(x)&=p(x)\cdot q(x)\\&=(x^3-3x+2)(3x^2-6x+5)\\&=3x^5-6x^4+5x^3-9x^3+18x^2-15x+6x^2-12x+10\\&=3x^5-6x^4-4x^3+24x^2-27x+10\end{split}
$$
## Division of Polynomials
It is important to realize that $L_D$ is NOT an operator that you can have in a ring, or field, or group.

Division normally looks like,
$$
\begin{array}{c}m=qn+r\\\frac{m}n=q+\frac{r}n\end{array}
$$
### Division Property
If we have $f(x)$ and $g(x)$ where $f(x)\ge g(x)$ and $g(x)\ne 0$, then
$$
f(x)=g(x)\cdot q(x)+r(x)\,\,\,\,\,\,\,\,\text{ where q,r are unique, and deg}(r(x))<\text{deg}(g(x))
$$
### Example
We have,
$$
f(x)=x^3-x^2+2x-3\,\,\,\,\,\,\,\text{ and }\,\,\,\,\,\, g(x)=x-2
$$
Long division of $f(x)/g(x)$ gives
$$
\begin{array}{c}\text{quotient q(x): }x^2+x+4\\\text{remainer r(x): }5\end{array}
$$
So,
$$
f(x)=(x-2)\cdot(x^2+x+4)+5
$$
And,
$$
p(x)=x^2+5x+6=(x+2)(x+3)+0
$$

The **GCD (Greatest Common Division)**: Let $F$ be a field. A monic polynomial $d(x)$ is the GCD of polynomials $p(x),q(x)\in F[x]$ if $d(x)$ is the highest possible degree polynomial which is a factor of both $p(x)$ and $q(x)$.
So, $d(x)=\text{gcd}(p(x),q(x))$

Suppose $d(x)=\text{gcd}(p(x),q(x))$ in $F[x]$,
Then $\exists\, r(x)$ and $s(x)$ such that $d(x)=r(x)\cdot p(x)+s(x)\cdot q(x)$

## Analogous primes
We get irreducible elements 

$f(x)\in F(x)$, non-constant polynomial

We can say that $f(x)$ is *reducible* over $F$ if and only if it can be factored as a product of two non-constant polynomials.

Let 
$$
f(x)=x^2-3=(x+\sqrt 3)(x-\sqrt 3)\,\,\,\,\,\,\text{in }\mathbb{R}[x],\mathbb{C}[x]
$$
but $f(x)$ is not reducible in $\mathbb{Q}[x]$
## The Factor Theorem
Let $[F,+,\cdot]$ be a field. An element $a\in F$ is a *zero* of a polynomial $f(x)\in F[x]$ if and only if $x-a$ is a factor of $f(x)$ in $F[x]$

N.B. A zero is simply the root of a polynomial. 

**Proof**
$$
\implies: \text{ Assume $a\in F$ is a zero of $f(x)$. Let $x-a$ be a factor,}
$$
$$
g(x)=x-a
$$
By the Division property
$$
f(x)=g(x)\cdot q(x)+r(x)\,\,\,\,\,\,\,\, q(x), r(x)\in F[x],\,\,\,\,\text{deg}(r(x))<\text{deg}(g(x))
$$
Then
$$
\text{deg}(g(x))=1\,\,\,\,\,\,\,\text{ so }r(x)=c \text{ (constant)}\in F
$$
As $a\in F$ is a zero of $f(x)$, then $f(a)=0$.

This means
$$
\begin{split}f(x)&=(x-a)\cdot q(c)+c\\0&=(a-a)\cdot q(x)+c\Rightarrow c=0\end{split}
$$
$$
f(x)=(x-a)\cdot q(x)+0
$$
This shows that $x-a$ is a factor. 

Prove the backwards direction as a homework.




