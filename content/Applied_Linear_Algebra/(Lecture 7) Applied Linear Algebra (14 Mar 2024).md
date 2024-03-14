---
title: Lecture 7
date: 14 Mar 2024
---
# Complex Field, Eigenvalues and Eigenvectors, Diagonalization
## Example
Inner products over $\mathbb{C}$ 
- $\langle \bar u,\bar v\rangle =\langle \bar v,\bar u\rangle$
- Linearity in the first argument
$$
\langle c\bar u,\bar v\rangle=c\langle\bar u,\bar v\rangle
$$
$$
\langle \bar u,c\bar v\rangle=c^*\langle \bar u,\bar v\rangle
$$
## Example
$P^2$ over $\mathbb R$
$$
\langle p,q\rangle=\int_{-1}^1 p(t)q(t)\,dt
$$
$P^2$ over $\mathbb C$
$$
\langle p,q\rangle=\int_{-1}^1p(t)q(t)^*\, dt=\int_{-1}^1 \left(q(t)p(t)^*\right)^*\, dt=\langle q,p\rangle^*
$$
where $*$ represents the conjugate of the number

$\mathbb{R}^n$
$$
\bar u=(u_1,\dots,u_n)^T\,\,\,\,\,\,\,\,\bar v=(v_1,\dots,v_n)^T
$$
$$
\langle\bar u,\bar v\rangle=\sum_{i=1}^n u_i\, v_i
$$
$\mathbb{C}^n$
$$
\langle\bar u,\bar v\rangle=\sum_{i=1}^n u_iv_i^*=\left(\sum_{i}v_iu_i^*\right)^*=\langle\bar v,\bar u\rangle^*
$$
$$
\langle a\bar u,\bar v\rangle=\sum_i au_iv_i^*=a\sum_i u_iv_i^*=a\langle \bar u,\bar v\rangle
$$
## Diagonalization
$$
A=P\,\,\Lambda P^{-1}
$$
$$
\begin{bmatrix}\\ \bar v_1,\bar v_2,\dots,\bar v_n\\ \dots\end{bmatrix}\begin{bmatrix}\lambda_1&&&\\&\lambda_2\\&&\ddots\\&&&\lambda_n\end{bmatrix}
$$

$$
A\in \mathbb{C}^{n\times n}
$$
where n is linearly independent eigenvectors!

Algebraic multiplicity of a root $\rightarrow$ same number of eigenvectors.

$$
A^m=(P\,\,\Lambda P^{-1})(P\,\,\Lambda P^{-1})\dots(P\,\,\Lambda P^{-1})=P\,\,\Lambda^mP^{-1}
$$
$$
\Lambda^m=\begin{bmatrix}\lambda_1^m&&\\&\ddots&\\&&\lambda_n^m\end{bmatrix}
$$
### Example
$$
A=\begin{bmatrix}6*-8\\4&-6\end{bmatrix}
$$
$$
0=\text{det}(A-\lambda I)=\left|\begin{array}{cc}6-\lambda&-8\\4&-6-\lambda\end{array}\right|=(6-\lambda)(-6-\lambda)+32=\lambda^2-36+32=\lambda^2-4=0
$$
So,
$$
\lambda_1=2\,\,\,\,\,\,\,\,\lambda_2=-2
$$
When $\lambda_1=2$
$$
\text{ker}(A-\lambda_1 I)=\text{ker}(A-2I)
$$
$$
\begin{bmatrix}4&-8\\4&-8\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}
$$
We only need to find one solution,
$$
4x-8y=0\,\,\,\,\,\, x-2y=0
$$
$$
\bar v_1=\begin{bmatrix}2\\1\end{bmatrix}
$$
When $\lambda_2=-2$
$$
\text{ker}(A+2I)
$$
$$
A+2I=\begin{bmatrix}8&-8\\4&-4\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}
$$
Finding the solution
$$
\begin{array}{c}8x-8y=0\\ x-y=0\end{array}\,\,\,\,\,\,\,\bar v_2=\begin{bmatrix}1\\1\end{bmatrix}
$$
So,
$$
\Lambda=\begin{bmatrix}2&0\\0&-2\end{bmatrix}
$$
$$
P=\begin{bmatrix}2&1\\1&1\end{bmatrix}\,\,\,\,\,\,\,\text{det}(P)=2-1=1\,\,\, P^{-1}=\begin{bmatrix}1&-1\\-1&2\end{bmatrix}
$$
$$
A=\begin{bmatrix}2&1\\1&1\end{bmatrix}\begin{bmatrix}2&0\\0&-2\end{bmatrix}\begin{bmatrix}1&-1\\-1&2\end{bmatrix}
$$
____
### Inverse problem
Matrix B has eigenvalues 3,-5,6 and corresponding eigenvectors of $\begin{pmatrix}2\\-3\\-1\end{pmatrix},\begin{pmatrix}2\\1\\-1\end{pmatrix},\begin{pmatrix}1\\6\\16\end{pmatrix}$. Find B.

$$
P=\begin{bmatrix}2&2&1\\-3&1&6\\-1&-1&16\end{bmatrix}\,\,\,\,\,\,\,\Lambda=\begin{bmatrix}3&0&0\\0&-5&0\\0&0&6\end{bmatrix}
$$
$$
\begin{split}B&=P\,\,\Lambda P^{-1}\\&=\begin{bmatrix}-2&-4&2\\-2&1&2\\4&2&5\end{bmatrix}\end{split}\,\,\,\,\,\,\,\Lambda=P^{-1}\,\,B P
$$
___
## Example
Consider a Fibonacci sequence
$$
F_1=1,F_2=1,F_n=F_{n-1}+F_{n-2}
$$
Let a transformation $T\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}y\\x+y\end{pmatrix}$
Show that $T^n\begin{pmatrix}0\\1\end{pmatrix}=\begin{pmatrix}F_n\\F_{n+1}\end{pmatrix}\,\,\,\,\, n\ge 1$

We can show this by Proof of Induction,
For $n=1$
$$
T\begin{pmatrix}0\\1\end{pmatrix}=\begin{pmatrix}1\\1+0\end{pmatrix}=\begin{pmatrix}1\\1\end{pmatrix}=\begin{pmatrix}F_1\\F_2\end{pmatrix}
$$
Assume $n=k$ is true $T^k\begin{pmatrix}0\\1\end{pmatrix}=\begin{pmatrix}F_k\\F_{k+1}\end{pmatrix}$
For $n=k+1$
$$
T^{k+1}\begin{pmatrix}0\\1\end{pmatrix}=T\left(T^k\begin{pmatrix}0\\1\end{pmatrix}\right)=T\begin{pmatrix}F_k\\F_{k+1}\end{pmatrix}=\begin{pmatrix}F_{k+1}\\F_k+F_{k+1}\end{pmatrix}=\begin{pmatrix}F_{k+1}\\F_{k+2}\end{pmatrix}
$$
Find eigenvalues and eigenvectors of T
$$
T=\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}y\\x+y\end{pmatrix}\,\,\,\,\,\,\,\, T=\begin{bmatrix}0&1\\1&1\end{bmatrix}
$$
$$
\text{det}(T-\lambda I)=\left|\begin{array}{cc}-\lambda&1\\1&1-\lambda\end{array}\right|=-\lambda(1-\lambda)-1=\lambda^2-\lambda-1
$$
$$
\lambda_1=\frac{1+\sqrt{1+4}}{2}=\frac{1+\sqrt 5}2,\,\,\,\,\,\,\,\lambda_2=\frac{1-\sqrt 5}2
$$
For $\lambda_1: \bar v_1$
$$
\text{ker}(T-\lambda_1 I)=\begin{bmatrix}-\lambda_1&1\\1&1-\lambda_1\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}
$$
$$
-\lambda_1x+y=0\,\,\,\,\,\,\,\bar v_1=\begin{bmatrix}1\\\lambda_1\end{bmatrix}
$$
For $\lambda_2$
$$
\text{ker}(T-\lambda_2 I):\,\begin{bmatrix}-\lambda_2&1\\1&1-\lambda_2\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}
$$
$$
\bar v_2=\begin{bmatrix}1\\\lambda_2\end{bmatrix}
$$
So,
$$
\bar v_1=\begin{bmatrix}1\\\frac{1+\sqrt 5}2\end{bmatrix},\,\,\,\,\,\bar v_2=\begin{bmatrix}1\\\frac{1-\sqrt 5}2\end{bmatrix}
$$
By considering $T^n\begin{pmatrix}0\\1\end{pmatrix}$, find an expression for $F_n$
$$
P=\begin{bmatrix}1&1\\\frac{1+\sqrt 5}2&\frac{1-\sqrt 5}2\end{bmatrix}\,\,\,\,\,\,\,\,\Lambda=\begin{bmatrix}\frac{1+\sqrt 5}2&0\\0&\frac{1-\sqrt 5}2\end{bmatrix}
$$
$$
\text{det}(P)=\frac{1-\sqrt 5}{2}-\frac{1+\sqrt 5}{2}=-\sqrt 5\,\,\,\,\,\,\,\,\, P^{-1}=-\frac{1}{\sqrt 5}\begin{bmatrix}\frac{1-\sqrt 5}2&-1\\-\frac{1+\sqrt 5}2&1\end{bmatrix}
$$
So,
$$
T=-\frac{1}{\sqrt 5}\begin{bmatrix}1&1\\\lambda_1&\lambda_2\end{bmatrix}\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}\begin{bmatrix}\lambda_2&-1\\-\lambda_1&1\end{bmatrix}
$$
$$
\begin{pmatrix}F_n\\F_{n+1}\end{pmatrix}=T^n\begin{pmatrix}0\\1\end{pmatrix}=-\frac{1}{\sqrt 5}\begin{bmatrix}1&1\\\lambda_1&\lambda_2\end{bmatrix}\begin{bmatrix}\lambda_1^n&0\\0&\lambda_2^n\end{bmatrix}\begin{bmatrix}\lambda_2&-1\\-\lambda_1&1\end{bmatrix}\begin{bmatrix}0\\1\end{bmatrix}
$$
$$
\begin{split}=&-\frac{1}{\sqrt 5}\begin{bmatrix}1&1\\\lambda_1&\lambda_2\end{bmatrix}\begin{bmatrix}\lambda_1^n&0\\0&\lambda_2^n\end{bmatrix}\begin{bmatrix}-1\\1\end{bmatrix}\\=&-\frac{1}{\sqrt 5}\begin{bmatrix}1&1\\\lambda_1&\lambda_2\end{bmatrix}\begin{bmatrix}-\lambda_1^n\\\lambda_2^n\end{bmatrix}\\=&-\frac 1{\sqrt5}\begin{bmatrix}-\lambda_1^n+\lambda_2^n\\-\lambda_1^{n-1}+\lambda_2^{n+1}\end{bmatrix}=\begin{bmatrix}F_n\\F_{n+1}\end{bmatrix}\end{split}
$$
$$
F_n=-\frac{1}{\sqrt 5}\begin{bmatrix}-\lambda_1^n+\lambda_2^n\end{bmatrix}=\frac{1}{\sqrt 5}\begin{bmatrix}\left(\frac{1+\sqrt 5}{2}\right)^n-\left(\frac{1-\sqrt 5}2\right)^n\end{bmatrix}
$$








