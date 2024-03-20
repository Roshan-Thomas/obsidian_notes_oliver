---
title: Lecture 11
date: 20 Mar 2024
---
# Vector space
Definition: Let $F$ be a field. We call this the scalar field. We define a vector space over the scalar field as the set $V$ with the following operations:
- Vector Addition $V+V\rightarrow V$,   $\vec v+\vec u\rightarrow \vec w$
- Scalar multiplication: $F\cdot V\rightarrow V$,      $c\cdot\vec v\rightarrow \vec w$

(V1) $[V,+]$ is an Abelian group
(V2) Associativity of scalar multiplication: $\forall\, a,b\in F$ and $\vec v\in V$ then $(a\cdot_F b)\cdot \vec v=a\cdot\overbrace{(b\cdot\vec v)}^{\vec w}$

(V3) Distributivity of scalar addition over scalar multiplication: $\forall\, a,b\in F$ and $\vec v\in V$ then $(a+_F b)\cdot \vec v=(a\cdot \vec v)+(b\cdot \vec v)$

(V4) Distributivity of vector addition over scalar multiplication: $\forall\, a\in F,$ and $\vec v,\vec u\in V$ then $a\cdot(\vec v+\vec w)=(a\cdot \vec v)+(a\cdot \vec u)$

(V5) Scalar multiplicative identity: $\exists\, 1\in F$ such that $1\cdot \vec v=\vec v$

### Example
We have a general polynomial 
$$
f(x)=a_0+a_1x+a_2x+\dots+a_nx^n,\,\,\,\,\,\,\,\,\,\text{ where }a_i\in \mathbb{R}
$$

Showing vector addition $f(x)$ and $g(x)
$$
f(x)+g(x)=(a_0+b_0)+(a_1+b_1)x+\dots+(a_n+b_n)x^n
$$

Showing scalar multiplication $c\in \mathbb{R}$
$$
cf(x)=ca_0+ca_1x+\dots+ca_nx^n
$$
So, if we had
$$
(c\cdot k)f(x)=cka_0+cka_1x+\dots+ckx^n=c\cdot(ka_0+ka_1x+ka_nx^n)=c\cdot(k\cdot f(x))
$$

Scalar multiplicative identity is 1

This shows that polynomials are a vector space
### Example
$\mathbb{Q}(\sqrt 2)$ is a field of all real numbers of the form $p+\sqrt 2q$ where $p,q\in \mathbb{Q}$. 

This forms a vector space over $\mathbb{Q}$

Showing vector addition
$$
(p+\sqrt q)+(r+\sqrt 2 s)=(p+_Q r)+(q+_R s)\sqrt 2
$$
Showing scalar multiplication
$$
r(p+\sqrt 2 q)=(r\cdot_Q p)+(r\cdot_Q q)\sqrt 2
$$
### Example
The set $C(D, \mathbb{R})$ of all continuous real-valued functions defined over a given subset $D\subseteq\mathbb{R}$. This is a *real vector space*.

Showing vector addition,
$\begin{array}{c}x\mapsto f(x)\\ x\mapsto g(x)\end{array}$ are both continuous functions then so will be $x\mapsto f(x)+g(x)$

Showing scalar multiplication: $c\in \mathbb{R}$
$x\mapsto f(x)$ continuous functions over D then $x\mapsto cf(x)$
___
# Basis
- A set of vectors is *linearly dependent* if one of the vectors can be expressed as a weighted sum of all the others. 
	- If none of the vectors can be expressed as a weighted sum of the others, the set is *linearly independent*. 

- Elements $\vec v_1,\dots,\vec v_n$ of a vector space $V$ are
	- said to *span* $V$ if $\exists\, \vec n \in V,\,\forall\, c_1,\dots,c_n\in F$ such that $\vec u=c_1\vec v_1+c_2\vec v_2+\dots+c_n\vec v_n$
	- said to form a *basis* of $V$ if they are also linearly independent.