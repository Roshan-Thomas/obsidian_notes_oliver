---
title: Lecture 4
date: 16 Feb 2024
---
We considered a vector space (last time) 
$$
V=\text{span}\{1,t\}
$$
$$
\langle u,v\rangle=\int_0^1 uv\, dt
$$
$$
\begin{array}{c}x_1=3t+5\\ x_2=-2t+7\end{array} \,\,\,\,\,\,\,\langle x_1,x_2\rangle=-6\langle t,t\rangle+11\langle t,1\rangle+35\langle 1,1\rangle
$$
___
# Orthogonal Basis and Gram-Schmidt Process
Orthogonal Basis contains all the vectors are such that the inner product between two vectors are 0
$$
\text{B is an orthogonal basis if }B=\{\bar v_1,\bar v_2,\dots,\bar v_n\}\,\,\,\,\,\, \text{ such that }\langle \bar v_i,\bar v_j\rangle=0\text{ if }i\ne j
$$

Consider $R^3$ and an inner product
$$
\langle\bar x,\bar y\rangle=2\left(\sum_{i=1}^3 x_iy_i\right)-\left(\sum_{i=1}^2x_iy_{i+1}+x_{i+1}y_i\right)
$$
$$
\begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}\begin{bmatrix}y_1\\y_2\\y_3\end{bmatrix}
$$
Show that this is an inner product and construct an orthogonal basis.

To show its an inner product, we need to show symmetry and linearity 
$$
\langle\bar x,\bar y\rangle=\langle\bar y,\bar x\rangle
$$
$$
\langle\lambda \bar x,\bar y\rangle=\lambda\langle\bar x,\bar y\rangle
$$
To show positivity
$$
\begin{split}\langle\bar x,\bar x\rangle&=2\left(\sum_{i=1}^3 x_i^2\right)-2\left(\sum_{i=1}^2x_ix_{i+1}\right)\\&= 2(x_1^2+x_2^+x_3^2)\\&=x_1^2+x_3^2+\sum_{i=1}^2 x_i^2+\sum_{i=1}^2x_{i+1}^2-\sum_{i=1}^2 2x_i x_{i+1}\\&=x_1^2+x_3^2+\sum_{i=1}^2\left(x_i^2+x_{i+1}^2-2x_ix_{i+1}\right)^2\\ &=x_1^2+x_3^2+\sum_{i=1}^2(x_i-x_{i+1})^2 \ge 0 \end{split}
$$
Each of the terms are non-negative

So to find when $\langle\bar x,\bar x\rangle=0$
$$
\begin{array}{c}x_1^2=0\Rightarrow x_1=0\\ x_3=0\end{array}\,\,\,\,\,\,\,\,\,\,\begin{array}{c}x_1-x_2=0\\ x_2-x_3=0\end{array}\Rightarrow x_2=0
$$

To show that its an orthogonal basis
$$
R^3=\text{span}\left\{\begin{bmatrix}1\\0\\0\end{bmatrix},\begin{bmatrix}0\\1\\0\end{bmatrix},\begin{bmatrix}0\\0\\1\end{bmatrix}\right\}
$$
**Gram-Schmidt Process**

$$
\bar v_1=\bar w_1\,\,\,\,\,\,\,\,\bar v_k=\bar w_k-\sum_{j=1}^{k-1}\frac{\langle\bar v_j,\bar w_k\rangle}{||\bar v_j||^2}\bar v_j
$$
$$
\bar v_1=\begin{bmatrix}1\\0\\0\end{bmatrix}\,\,\,\,\,\,\,||\bar v_1||^2=\langle \bar v_1,\bar v_1\rangle=2(1+0+0)-2(0+0)=2
$$
$$
\bar v_2=\begin{bmatrix}0\\1\\0\end{bmatrix}-\frac{\langle\bar v_1,\bar w_2\rangle}{||\bar v_1||^2}\bar v_1\,\,\,\,\,\,\,\,\,\, \langle v_1,\bar w_2\rangle=2(0+0+0)-(1+0+0+0)=-1
$$
$$
=\begin{bmatrix}0\\1\\0\end{bmatrix}-\frac{-1}2\begin{bmatrix}1\\0\\0\end{bmatrix}=\begin{bmatrix}\frac 1 2\\1\\0\end{bmatrix}
$$
The norm 
$$
\langle\bar v_2,\bar v_2\rangle=2\left(\frac 1 4+1+0\right)-\left(\frac 1 2 +\frac 1 2 +0+0\right)=\frac 5 2 -1=\frac 3 2
$$

$$
\begin{bmatrix}1\\0\\0\end{bmatrix}\begin{bmatrix}0\\0\\1\end{bmatrix}
$$
$$
\langle\bar v_1,\bar w_3\rangle=2(0+0+0)-(0+0+0+0)=0
$$
Computing the others
$$
\begin{bmatrix}\frac 1 2 \\1\\0\end{bmatrix}\begin{bmatrix}0\\0\\1\end{bmatrix}
$$
$$
\langle\bar v_2,\bar w_3\rangle=2(0+0+0)-\left(\frac 1 2\times 0+0\times 1+1\times 1+0\times 0\right)=-1
$$
Plugging back into equation
$$
\bar v_3=\begin{bmatrix}0\\0\\1\end{bmatrix}-0\bar v_1+\frac 1 {\frac 3 2}\begin{bmatrix}\frac 1 2\\1\\0\end{bmatrix}=\begin{bmatrix}0\\0\\1\end{bmatrix}+\frac 2 3 \begin{bmatrix}\frac 1 2\\1\\0\end{bmatrix}=\begin{bmatrix}\frac 1 3\\\frac 2 3\\1\end{bmatrix}
$$
$$
B=\left\{\begin{bmatrix}1\\0\\0\end{bmatrix},\begin{bmatrix}\frac 12\\1\\0\end{bmatrix},\begin{bmatrix}\frac 1 3\\\frac 2 3\\1\end{bmatrix}\right\}
$$
___
### Why care about orthogonal bases?
Lets take an orthogonal basis
$$
\{\bar v_1,\bar v_2,\dots,\bar v_n\}-\text{orthogonal basis of V}
$$
$$
\bar w_1=\sum_{i=1}^n a_i\bar v_i
$$
$$
\bar w_2=\sum_{i=1}^n b_i\bar v_i
$$
$$
\langle \bar w_1,\bar w_2\rangle=\left\langle\sum_{i=1}^n a_i\bar v_i,\sum_{j=1}^n b_j\bar v_j\right\rangle
$$
By linearity, we can extract elements out
$$
\begin{split}\rangle\bar w_1,\bar w_2\rangle=&\sum_i a_i\langle\bar v_i,\sum_j b_j\bar v_j\rangle\,\,\,\,\,\,\,\,\,\text{by linearity}\\ =&\sum_i a_i\rangle\sum_j b_j\bar v_j,\bar v_i\rangle\\=& \sum_i a_i\sum_j b_j\langle\bar v_j,\bar v_i\rangle\\ =&\sum_i\sum_j a_ib_j\langle\bar v_j,\bar v_i\rangle\,\,\,\,\,\,i\ne j\\=&\sum_i a_i b_i\langle \bar v_i,\bar v_i\rangle\end{split}
$$

Introducing an additional property
$$
B=\{\bar v_1,\bar v_2,\dots,\bar v_n\}\,\,\,text{ orthonormal }\rightarrow \langle \bar v_i,\bar v_j=0\,\,\,i\ne j\,\,\,\,\,\,\,\,\,||\bar v_i||=1
$$
in orthonormal basis
$$
\langle \bar w_1,\bar w_2\rangle=\sum_i a_i b_i
$$
___
We have a function $f$ to approximate
$$
p=\sum_i a_i p_i
$$
Minimize
$$
||f-p||^2\rightarrow \langle f-p,f-p\rangle=\langle f,f\rangle-2\sum_{i} a_i\langle p_i,f\rangle
$$
$$
\frac{\partial||f-p||^2}{\partial a_i}=0\,\,\,\,\,\,\,\,\, a_i=\frac{\langle f,p_i}{||p_i||^2}
$$
#### Example
$P^2$ with inner product
$$
\langle p,q\rangle=p(0)q(0)+p(1)q(1)+p(2)q(2)
$$
Showing positivity 
$$
\langle p,p\rangle=(p(0))^2+(p(1))^2+(p(2))^2\ge 0
$$
$$
\langle p,p\rangle=0\,\,?
$$
It becomes zero when
$$
p(0)=0,\,\,p(1)=0,\,\,\, p(2)=0
$$
The only possibility for a quadratic to have more than 2 roots is when $p(x)=0$


