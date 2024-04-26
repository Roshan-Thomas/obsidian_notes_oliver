---
title: Lecture 10
date: 26 Apr 2024
---
**Important Correction**
$Q\in\mathbb{R}^{n\times n}$ is orthogonal $Q^TQ=I=QQ^T$

$Q\in\mathbb{R}^{n\times n}$ is orthogonal $Q^TQ=I$

for the least squares fitting, it is not true that if
$$
||Ax-b||\ne ||Rx-Q^Tb||\text{ where }QR=A
$$
but it is true that
$$
\text{argmin}_x\,\,||Ax-b||=\text{argmin}_x\,\,||Rx-Q^Tb||
$$
# QR factorization, Least Squares fitting (via QR)
$$
A=\underbrace{Q}_{\text{orthogonal}}\overbrace{R}^{\text{upper triangular}}
$$
The matrix that is chosen is
$$
A=\begin{bmatrix}1&1&0\\1&0&1\\0&1&1\end{bmatrix}
$$
We start with three vectors
$$
\bar u_1=\begin{bmatrix}1\\1\\0\end{bmatrix}\,\,\,\bar u_2=\begin{bmatrix}1\\0\\1\end{bmatrix}\,\,\,\bar u_3=\begin{bmatrix}0\\1\\0\end{bmatrix}
$$
Find an orthonormal basis (use the Gram-Schmidt Process)
$$
\bar w_1=\begin{bmatrix}1\\1\\0\end{bmatrix}\xmapsto{\text{normalise}} ||\bar w_1||=\sqrt 2\,\,\,\,\bar v_1=\frac{1}{\sqrt 2}\begin{bmatrix}1\\1\\0\end{bmatrix}
$$
$$
\bar w_2=\begin{bmatrix}1\\0\\1\end{bmatrix}-(\bar v_1\cdot \bar u_2)\bar v_1=\begin{bmatrix}1\\0\\1\end{bmatrix}-\begin{bmatrix}1\\0\\1\end{bmatrix}-\left(\begin{bmatrix}1\\0\\1\end{bmatrix}\cdot\begin{bmatrix}1/\sqrt 2\\1/\sqrt 2\\0\end{bmatrix}\right)\begin{bmatrix}1/\sqrt 2\\1/\sqrt 2\\0\end{bmatrix}=\begin{bmatrix}1/2\\-1/2\\1\end{bmatrix}
$$
$$
\xmapsto{\text{normalise}} ||\bar w_2||=\sqrt{\frac 1 4+\frac 1 4+1}=\sqrt{\frac{3}2}
$$
$$
\bar v_2=\sqrt{\frac 2 3}\begin{bmatrix}1/2\\-1/2\\1\end{bmatrix}=\begin{bmatrix}1/\sqrt 6\\-1/\sqrt 6\\\sqrt{2/3}\end{bmatrix}
$$
$$
\begin{split}\bar w_3&=\begin{bmatrix}0\\1\\1\end{bmatrix}-(\bar v_1\cdot \bar u_3)\begin{bmatrix}1/\sqrt 2\\1/\sqrt 2\\0\end{bmatrix}-(\bar v_2\cdot\bar u_3)\begin{bmatrix}1/\sqrt 6\\-1/\sqrt 6\\\sqrt{2/3}\end{bmatrix}\\ &=\begin{bmatrix}0\\1\\1\end{bmatrix}-\frac{1}{\sqrt 2}\begin{bmatrix}1/\sqrt 2\\1/\sqrt 2\\0\end{bmatrix}-\frac{1}{\sqrt 6}\begin{bmatrix}1/\sqrt 6\\-1/\sqrt 6\\\sqrt{2/3}\end{bmatrix}=\begin{bmatrix}-1/3\\1/3\\1/3\end{bmatrix}\end{split}
$$
$$
Q=\begin{bmatrix}1/\sqrt 2&1/\sqrt 6&-1/\sqrt 3\\1/\sqrt 2&-1/\sqrt 6&1/\sqrt 3\\0&\sqrt{2/3}&1/\sqrt 3\end{bmatrix}
$$
$$
\begin{split}R&=\begin{bmatrix}\bar u_1\cdot \bar v_1&\bar u_2\cdot \bar v_1&\bar u_3\cdot \bar v_1\\0&\bar u_2\cdot\bar v_2&\bar u_3\cdot \bar v_2\\0&0&\bar u_3\cdot\bar v_3\end{bmatrix}\\ &=\begin{bmatrix}2/\sqrt 2&1/\sqrt 2&1/\sqrt 2\\0&3/\sqrt 6&1/\sqrt 6\\0&0&2/\sqrt 3\end{bmatrix}\end{split}
$$
$$
\underbrace{\begin{bmatrix}1&1&0\\1&0&1\\0&1&1\end{bmatrix}}_A=\underbrace{\begin{bmatrix}1/\sqrt 2&1/\sqrt 6&-1/\sqrt 3\\1/\sqrt 2&-1/\sqrt 6&1/\sqrt 3\\0&\sqrt{2/3}&1/\sqrt 3\end{bmatrix}}_Q\underbrace{\begin{bmatrix}2/\sqrt 2&1/\sqrt 2&1/\sqrt 2\\0&3/\sqrt 6&1/\sqrt 6\\0&0&2/\sqrt 3\end{bmatrix}}_R
$$
Other types of decompositions are
- LU decomposition
- Diagonailzation of Jordon
- Cholesky Decomposition $A=U^*U$, $U^*=\bar U^T$ 

### Example
Let $W=\text{span }\left\{\begin{bmatrix}1\\2\\-1\end{bmatrix},\begin{bmatrix}2\\-3\\-1\end{bmatrix}\right\}\subset\mathbb{R}^3$

Find $\bar w^*\in \mathbb{R}^3$ closest to $\bar b=\begin{bmatrix}1\\0\\0\end{bmatrix}$

$$
x_1\begin{bmatrix}1\\2\\-1\end{bmatrix}+x_2\begin{bmatrix}2\\-3\\-1\end{bmatrix}=\begin{bmatrix}1\\0\\0\end{bmatrix}
$$
Find $\bar x=\begin{bmatrix}x_1\\x_2\end{bmatrix}$ such that $||A\bar x-\bar b||$ is minimal $A=\begin{bmatrix}1&2\\2&-3\\-1&-1\end{bmatrix}$
$$
\text{argmin}_x\,\,||A\bar x-\bar b||=\text{argmin}_x\,\,||R\bar x-Q^T\bar b||
$$
$QR=A$
Gram-schmidth $\bar u_1=\begin{bmatrix}1\\2\\-1\end{bmatrix}$, $\bar u_2=\begin{bmatrix}2\\-3\\-1\end{bmatrix}$
$$
\bar w_1=\begin{bmatrix}1\\2\\-1\end{bmatrix}\xmapsto{\text{normalise}}\bar v_1=\frac{1}{\sqrt 6}\begin{bmatrix}1\\2\\-1\end{bmatrix}=\begin{bmatrix}1/\sqrt 6\\2/\sqrt 6\\-1/\sqrt 6\end{bmatrix}
$$
$$
\bar w_2=\begin{bmatrix}2\\-3\\-1\end{bmatrix}-(\bar v_1\cdot\bar u_2)\bar v_1=\begin{bmatrix}2\\-3\\-1\end{bmatrix}-\left(\frac{3}{\sqrt 6}\right)\begin{bmatrix}1/\sqrt 6\\2/\sqrt 6\\-1/\sqrt 6\end{bmatrix}=\begin{bmatrix}5/2\\-2\\-3/2\end{bmatrix}
$$
$$
\xmapsto{\text{normalise}} ||\bar w_2||=\sqrt{\frac{25}4+5+\frac{4}9}=\sqrt{\frac{56}4}=\frac{5\sqrt 2}2\,\,\,\,\bar v_2=\begin{bmatrix}1/2\\-\frac{4}{5\sqrt2}\\\frac{3}{5\sqrt 2}\end{bmatrix}
$$
$$
\bar v_2=\begin{bmatrix}\frac{\sqrt 2}2\\-2\sqrt 2/5\\-3\sqrt 2/10\end{bmatrix}\,\,\,\,Q=\begin{bmatrix}1/\sqrt 6&\sqrt{2}2\\2/\sqrt 6&-2\sqrt 2/5\\-1/\sqrt{6}&-3\sqrt 2/10\end{bmatrix}
$$
$$
R=\begin{bmatrix}\bar u_1\cdot\bar v_1&\bar u_2\cdot\bar v_1\\0&\bar u_2\cdot v_2\end{bmatrix}=\begin{bmatrix}\sqrt 6&\frac{-\sqrt 6}2\\0&\frac{5\sqrt 2}4\end{bmatrix}
$$
$$
A\bar x-\bar b\rightarrow R\bar x-Q^T\bar b=0
$$
$$
\bar{\hat h}=Q^T\bar b=\begin{bmatrix}1/\sqrt 6&2/\sqrt 6&-1/\sqrt 6\\\sqrt 2/2&-2\sqrt 2/5&-3\sqrt 2/10\end{bmatrix}\begin{bmatrix}1\\0\\0\end{bmatrix}=\begin{bmatrix}1/\sqrt 6\\\sqrt 2/2\end{bmatrix}
$$
$$
R\bar x=\bar{\hat b}
$$
$$
\begin{bmatrix}\sqrt 6&\frac{-\sqrt 6}2\\0&\frac{5\sqrt 2}{2}\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}1/\sqrt 6\\\frac{\sqrt 2}2\end{bmatrix}
$$


$$
\begin{array}{c}\sqrt 6 x_1-\frac{\sqrt 6}{10}=\frac{\sqrt 6}6\\ x_1=\frac{1}6+\frac 1{10}=\frac{4}{15}\end{array}
$$
$$
\bar w^*=\frac{4}{15}\begin{bmatrix}1\\2\\-1\end{bmatrix}+\frac 1 5\begin{bmatrix}2\\-3\\-1\end{bmatrix}=\begin{bmatrix}2/3\\-1/15\\-7/15\end{bmatrix}
$$