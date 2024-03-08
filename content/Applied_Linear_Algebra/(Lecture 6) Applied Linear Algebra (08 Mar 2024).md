---
title: Lecture 6
date: 08 Mar 2024
---
# Recap
Matrix Representation
$$
V=P^2\,\,\,\,\,\,\,\, B=\{1,t,t^2\}
$$
$$
L[x(t)]=\int_0^1 x(t-\tau)d\tau
$$
$$
\mathcal{M}=\begin{bmatrix}1&-\frac 1 2&\frac 1 3\\ 0&1&-1\\0&0&1\end{bmatrix}
$$
$$
x=6+2t-3t^2\,\,\,\,\,\,\,\,\,\begin{bmatrix}6\\2\\-3\end{bmatrix}
$$
$$
L[6+2t-3t^2]=\begin{bmatrix}1&-\frac 1 2&\frac 1 3\\0&1&-1\\0&0&1\end{bmatrix}\begin{bmatrix}6\\2\\-3\end{bmatrix}=\begin{bmatrix}4\\5\\-3\end{bmatrix}=4+5t-3t^2
$$
____
# Dual Basis

**Dual Space**: is a set of all measurements on $V$

**Dual Basis**: It is a basis for the Dual Space.

*The* Dual Basis: Consider a vector space $V$ with a basis $B=\{\bar v_1,\bar v_2,\dots,\bar v_n\}$. The dual basis $V^*$ is $\{l_1,l_2,\dots,l_n\}$ such that
$$
l_i(\bar v_j)=\begin{cases}0&\text{if i$\ne$ j}\\ 1&\text{if i$=$j}\end{cases}
$$
### Example
The basis of a second degree polynomial $P^2$ are 
$$
B=\{1,t,t^2\}
$$
Show that the Dual basis 
$$
\begin{array}{c}l_0(\bar x)=\bar x(0)\\ l_1(\bar x)=\bar x'(0)\\l_2(\bar x)=\frac 1 2\bar x''(0)\end{array}
$$


Evaluating
$$
\begin{array}{c}l_0(1)=1\\l_0(t)=0\\l_0(t^2)=0\end{array}\,\,\,\,\,\,\,\,\begin{array}{c}l_1(t)=0\\l_1(t)=1\\l_1(t^2)=0\end{array}\,\,\,\,\,\,\, \begin{array}{c}l_2(1)=0\\l_2(t)=0\\l_2(t^2)=1\end{array}
$$
N.B. A nice association is that the dual basis evaluates to an identity matrix
___
Why?
$$
\bar v=c_1\bar v_1+c_2\bar v_2+\dots+c_n\bar v_n
$$
$$
\begin{array}{c}l_1(\bar v)=c_1\\l_2(\bar v)=c_2\end{array}\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\dots \,\,\,\,\,\,\,\,\,\,\begin{array}{c}l_n(\bar v_n)=c_n\end{array}
$$
# Image and Kernel, Rank-Nullity, Homogenous and Inhomogeneous systems
If I have a transformation $T$, then the kernel of T
$$
\text{ker }T=\{\bar v:T\bar v=0\}
$$
Kernel is everything that send our function to zero.
The image of T
$$
\text{Img }T=\{\bar w\in W: T\bar v=\bar w\}
$$
___
### Example
Consider $V=P^2$ and $T:V\rightarrow V$
$$
T(\bar x(t))=(8t+2)\bar x(0)+(8t+2)\bar x'(0)-\frac 3 2(t^2+2t+2)\bar x''(0)
$$
- Find the matrix representation of T in the monomial basis
- Find $\text{Img T}$, $\text{ker T}$ and verify rank-nullity

Choosing our basis
$$
x_0=1\,\,\,\,\,\,\bar x_1=t\,\,\,\,\,\bar x_2=t^2
$$
$$
\begin{array}{c}T(\bar x_0)=8t+2=2\bar x_0+8\bar x_1\\ T(\bar x_1)=8t+2=2\bar x_0+8\bar x_1\\T(\bar x_2)=-\frac 3 2(t^2+2t+2)\times 2=-2t^2-6t-6=-6\bar x_0-6\bar x_1-3\bar x_2 \end{array}
$$

That's all the information needed to construct the matrix representation
$$
\mathcal{M}=\begin{bmatrix}2&2&-6\\8&8&-6\\0&0&3\end{bmatrix}
$$

Let's now find the answers to the second task (image, kernel, ...)

If we have any vector from that space
$$
\bar x=c_0+c_1t+c_2t^2
$$
We are trying to solve $T(\bar x)=0\, ?$
$$
\begin{bmatrix}2&2&-6\\8&8&-6\\0&0&-3\end{bmatrix}\begin{bmatrix}c_0\\c_1\\c_2\end{bmatrix}=\begin{bmatrix}0\\0\\0\end{bmatrix}
$$
Doing row operations
$$
R_2\mapsto R_2-4R_1\,\,\,\,\,\begin{bmatrix}2&2&-6\\0&0&18\\0&0&-3\end{bmatrix}\xmapsto{R_3\mapsto R_3-\frac 1 6 R_2}\begin{bmatrix}2&2&-6\\0&0&18\\0&0&0\end{bmatrix}\begin{bmatrix}c_0\\c_1\\c_2\end{bmatrix}=\begin{bmatrix}0\\0\\0\end{bmatrix}
$$
$$
c_2=0\,\,\,\,\,\,\,\,\, 2c_0+2c_1=0\,\,\,\,\,\,\,\begin{array}{c}c_1=\alpha\\c_0=-\alpha\end{array}
$$
$$
\text{ker T}=\{-\alpha+\alpha T\}=\text{span}\{-1+t\}
$$

Finding the image can be done from the column space,
$$
\text{Reduced $\mathcal{M}$} \begin{bmatrix}2&2&-6\\0&0&18\\0&0&0\end{bmatrix}
$$
$$
\mathcal{M}\begin{bmatrix}2&2&-6\\8&8&-6\\0&0&-3\end{bmatrix}
$$
The image 
$$
\begin{split}\text{img T}&=\text{span}\left\{\begin{bmatrix}2\\8\\0\end{bmatrix},\begin{bmatrix}-6\\-6\\-3\end{bmatrix}\right\}\\&=\text{span}\left\{2+8t,-6-6t-3t^2\right\}\\&=\text{span}\{1+4t,2+2t+t^2\}\end{split}
$$

$T:V\rightarrow W$
$$
\text{dim ker T}+\text{dim img T}=\text{dim V}
$$
$$
\text{ker T}=\text{span}\{1-t\}\,\,\,\,\,\,\,\,\,\begin{array}{c}\text{dim ker T}=1\\\text{dim img T}=2\\\text{dim $P^2$}=3\end{array}
$$
$$
1+2=3
$$

If we take any polynomial
$$
\bar y=a_0+a_1t+a_2t^2
$$
$$
T\bar y=\begin{bmatrix}2&2&-6\\8&8&-6\\0&0&-3\end{bmatrix}\begin{bmatrix}a_0\\a_1\\a_2\end{bmatrix}=\begin{bmatrix}2(a_0+a_2)-6a_2\\8(a_0+a_1)-6a_1\\-3a_2\end{bmatrix}=2(a_0+a_1)\begin{bmatrix}1\\4\\0\end{bmatrix}-3a_2\begin{bmatrix}2\\2\\1\end{bmatrix}
$$
____
Can I find $\bar z\in P^2$ such that 
$$
T(\bar z)=1-2t+t^2
$$
We know that the
$$
\text{img T}=\text{span}\{1+4t,2+2t+t^2\}
$$
Then
$$
T(\bar z)=1+2t+t^2-(1+4t)
$$
The **observation** is that 
$$
T(\bar z)\in \text{img T}\rightarrow \text{ has solutions!}
$$
The kernel
$$
\text{ker T}=\text{span}\{1-t\}\ne\{\bar 0\}\rightarrow \text{inf. solutions!}
$$

$$
\begin{split}T(\bar z+\kappa(1-t))=T(\bar z)\end{split}
$$



