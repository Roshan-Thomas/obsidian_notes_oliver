---
title: Lecture 8
date: 22 Mar 2024
---
# Recap
Diagonalization was given as 
$$
A=S\,\Lambda S^{-1}\Leftrightarrow (\lambda-\lambda_1)^{n_1}(\lambda-\lambda_2)^{n_2}\dots(\lambda-\lambda_k)^{n_k}
$$

____

# Gershgorin's Circle Theorem

### Gershgin's disks
Lets say you have a matrix, and you calculate the circles in the complex space that give us the eigenvalues. The matrix is centered at the diagonal $2,4,-3$
$$
\begin{bmatrix}2&-1&0\\1&4&-1\\-1&-1&-3\end{bmatrix}\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\begin{array}{cc}D_1:&|z-2|\le|-1|=1\\D_2:&|z-4|\le |1|+|-1|=2\\D_3:&|z+3|\le|-1|+|-1|=2\end{array}
$$
We plot it in the complex space,

![[Applied_Linear_Algebra/images/Pasted_image_20240322120936.png|500]]

The eigenvalues can be calculated (in MATLAB) as
$$
\begin{array}{c}\lambda_1=3\,\,\,\,\,\in D_1\cup D_2\\\lambda_2=\sqrt{10}\approx 3.16\,\,\,\,\,\,\in D_1\cup D_2\\\lambda_3=-\sqrt{10}\approx -3.16\,\,\,\,\,\in D_3\end{array}
$$
### Example
Lets have a diagonal matrix
$$
\begin{bmatrix}1&0\\0&5\end{bmatrix}
$$
The Gershgin's disks are
$$
\begin{array}{c}D_1:|z-1|\le 0\\D_2:|z-5|\le 0\end{array}
$$
The eigenvalues are 1 and 5 (can be calculated from the matrix itself).

### Example
Lets take another matrix
$$
\begin{bmatrix}0&1&0\\0&1&1\\0&-1&1\end{bmatrix}
$$
The disks are
$$
\begin{array}{c}D_1:|z-0|\le 1\\D_2:|z-1|\le 1\\D_3:|z-1|\le 1\end{array}
$$
![[Applied_Linear_Algebra/images/Pasted_image_20240322121520.png|500]]

The eigenvalues are inside the union of those two disks.

### Example
Lets take a matrix
$$
\begin{bmatrix}-\lambda&1&0\\0&1-\lambda&1\\0&-1&1-\lambda\end{bmatrix}=-\lambda\left((1-\lambda)^2+1\right)=0
$$
The eigenvalues are 
$$
\begin{array}{c}\lambda_1=0\\(1-\lambda)^2=1\end{array}
$$
# Jordan Normal (Canonical) Form
### Example
Let's take a matrix
$$
\begin{bmatrix}-1&-1\\4&-5\end{bmatrix}
$$
Finding the *eigenvalues*
$$
\begin{split}(-1-\lambda)(-5-\lambda)+4&=0\\\lambda^2+6\lambda+0&=0\\(\lambda+3)^2&=0\\\lambda&=-3\end{split}
$$
The algebraic multiplicity is 2

Finding the *eigenvectors*
$$
\text{ker}(A-\lambda I)=\text{ker}(A+3I)
$$
$$
\begin{bmatrix}2&-1\\4&-2\end{bmatrix}\begin{bmatrix}v_1\\v_2\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}
$$
$$
\begin{array}{c}2v_1-v_2=0\\ v_1=1\\ v_2=2\\\bar v=\begin{bmatrix}1\\2\end{bmatrix}\end{array}
$$
The geometric multiplicity is 1

Since the geometric multiplicity doesn't match the algebraic multiplicity, we have to find the generalized eigenvectors,
$$
\text{Search }\bar v_1,2
$$
$$
(A+3I)\bar v_{1,2}=\bar v_1
$$
$$
\begin{bmatrix}2&-1\\4&-2\end{bmatrix}\begin{bmatrix}w_1\\w_2\end{bmatrix}=\begin{bmatrix}1\\2\end{bmatrix}
$$
$$
\begin{array}{c}2w_1-w_2=1\\ w_1=1\\2-w_2=1\\w_2=1\end{array}
$$
So, the generalized eigenvector is
$$
\bar v_{1,2}=\begin{bmatrix}1\\1\end{bmatrix}
$$
Writing in the Jordan normal form
$$
A=S\, JS^{-1}
$$
$$
S=\begin{bmatrix}1&1\\\underbrace{2}_{\text{ker}(A-\lambda I)}&\underbrace{1}_{\text{ker}(A-\lambda I)^2}\end{bmatrix}
$$
$$
\text{det}(S)=1-2=-1\,\,\,\,\,\,\,\,\, S^{-1}=\begin{bmatrix}-1&1\\2&-1\end{bmatrix}
$$
$$
J=\begin{bmatrix}-3&1\\0&-3\end{bmatrix}
$$
Combining it all together
$$
A=\begin{bmatrix}1&1\\2&1\end{bmatrix}\begin{bmatrix}-3&1\\0&-3\end{bmatrix}\begin{bmatrix}-1&1\\2&-1\end{bmatrix}
$$
### Example
$$
B=\begin{bmatrix}1&1&1\\0&1&1\\0&0&1\end{bmatrix}
$$
Finding eigenvalues
$$
\left|\begin{array}{ccc}1-\lambda&1&1\\0&1-\lambda&1\\0&0&1-\lambda\end{array}\right|=(1-\lambda)^3=0\,\,\,\,\,\,\,\,\lambda=1
$$

$$
\text{ker}(B-\lambda I)=\text{ker}(B-I)
$$
$$
\begin{bmatrix}0&1&1\\0&0&1\\0&0&0\end{bmatrix}\begin{bmatrix}v_1\\v_2\\v_3\end{bmatrix}=\begin{bmatrix}0\\0\\0\end{bmatrix}
$$
$$
\begin{array}{c}v_3=0\\v_2=0\\v_1=1\\\bar v=\begin{bmatrix}1\\0\\0\end{bmatrix}\end{array}
$$
So,
$$
\bar v_{1,2}\,\,\,\,\,\,\text{ ker}(B-I)^2
$$
$$
\begin{array}{c}(B-I)\bar v_{1,2}=\bar v\\ \begin{bmatrix}0&1&1\\0&0&1\\0&0&0\end{bmatrix}\begin{bmatrix}w_1\\w_2\\w_3\end{bmatrix}=\begin{bmatrix}1\\0\\0\end{bmatrix}\\ w_3=0\\w_2=1\\w_1=1\\\bar v_{1,2}=\begin{bmatrix}1\\1\\0\end{bmatrix}\end{array}
$$
$$
\bar v_{1,3}\,\,\,\,\,\,\text{ker}(B-I)^3\,\,\,\,\,\,\, (B-I)\bar v_{1,3}=\bar v_{1,2}
$$
$$
\begin{bmatrix}0&1&1\\0&0&1\\0&0&0\end{bmatrix}\begin{bmatrix}u_1\\u_2\\u_3\end{bmatrix}=\begin{bmatrix}1\\1\\0\end{bmatrix}
$$
$$
\begin{array}{c}u_3=1\\u_2=0\\u_1=1\\\bar v_{1,3}=\begin{bmatrix}1\\0\\1\end{bmatrix}\end{array}
$$
So we can write,
$$
S=\begin{bmatrix}1&1&1\\0&1&0\\0&0&1\end{bmatrix}\,\,\,\,\,\,\,\,S^{-1}=\begin{bmatrix}1&-1&-1\\0&1&0\\0&0&1\end{bmatrix}
$$
The decomposition
$$
\begin{bmatrix}1&1&1\\0&1&1\\0&0&1\end{bmatrix}=\begin{bmatrix}1&1&1\\0&1&0\\0&0&1\end{bmatrix}\begin{bmatrix}1&1&0\\0&1&1\\0&0&1\end{bmatrix}\begin{bmatrix}1&-1&-1\\0&1&0\\0&0&1\end{bmatrix}
$$
### Example
$$
S=\begin{bmatrix}1&1&1\\2&0&1\\0&1&1\end{bmatrix}\,\,\,\,\,\,\, J=\begin{bmatrix}2&1&0\\0&2&0\\0&0&2\end{bmatrix}
$$
We need to extract the eigenvalues and eigenvectors from these matrices

The eigenvalue is $\lambda=2$ with algebraic multiplicity $=3$, and geometric multiplicity $=2$

The proper eigenvectors are $\begin{bmatrix}1\\2\\0\end{bmatrix}$ and $\begin{bmatrix}1\\1\\1\end{bmatrix}$ which is the first and third column in the S-matrix.
$$
(B-2I)\begin{bmatrix}1\\0\\1\end{bmatrix}=\begin{bmatrix}1\\2\\0\end{bmatrix}
$$

### Example
$$
J=\begin{bmatrix}1&1&0&0&0\\0&1&1&0&0\\0&0&1&0&0\\0&0&0&-2&1\\0&0&0&0&-2\end{bmatrix}
$$
We can identify the Jordon blocks as $\begin{bmatrix}1&1&0\\0&1&1\\0&0&1\end{bmatrix}$ and $\begin{bmatrix}-2&1\\0&-2\end{bmatrix}$. 

The eigenvalues are
$$
\lambda_1=1\,\,\,\,\,\,\text{A.M }= 3,\text{ G.M.}=1
$$
$$
\lambda_2=-2\,\,\,\,\,\,\text{A.M.}=2,\text{ G.M.}=1
$$
### Example
$$
J=\begin{bmatrix}1&1&0&0&0\\0&1&0&0&0\\0&0&1&0&0\\0&0&0&-2&1\\0&0&0&0&-2\end{bmatrix}
$$
The Jordan blocks are $\begin{bmatrix}1&1\\0&1\end{bmatrix}$, $\begin{bmatrix}1\end{bmatrix}$, $\begin{bmatrix}-2&1\\0&-2\end{bmatrix}$ 

The eigenvalues are 
$$
\begin{array}{c}\lambda_1=1\,\,\,\,\,\text{A.M.$=3$ G.M.$=2$}\\\lambda_2=-2\,\,\,\,\,\,\text{A.M.$=2$, G.M.$=1$}\end{array}
$$





