---
title: Lecture 17
date: 01 May 2024
---
# Revision
![[Discrete_Mathematics/images/Pasted_image_20240501100426.png]]

This is a zero-sum game.

**Part (a) (i)**
The payoff matrix for the game
$$
\text{Player A }\,\,\,\, \overbrace{\begin{array}{c|c|c}&H&T\\\hline H&0&1\\T&-1&2\end{array}}^{\text{Player B}}
$$

**Part (a) (ii)**
We are looking for the min-max (or best-worst case scenario). 

Brian's worst case scenario is the maximum of each column, and for Alexandra is the minimum of each row. 
$$
\begin{array}{c}\text{minmax B}=0\\ \text{maxmin A}=0\end{array}
$$
Since they are both equal, we can say that the optimal strategy is a pure strategy. 

![[Discrete_Mathematics/images/Pasted_image_20240501101043.png]]
$$
\begin{bmatrix}-1&-3&1\\4&3&-4\end{bmatrix}\rightarrow \begin{bmatrix}-3&1\\3&-4\end{bmatrix}
$$

**Part (b) (i)**
Player A being a rational player would never play column 1.

**Part (b) (ii)**
$$
\begin{array}{c}-3y_1+y_2\le 1\\3y_1-4y_2\le 1\end{array}
$$
They want to maximize $y_1+y_2=z$
$$
y_1,y_2\ge 0
$$
And the matrix turns into 
$$
\begin{bmatrix}1&5\\7&0\end{bmatrix}
$$
Writing the slack variables
$$
\begin{array}{cccc|c|c}y_1&y_2&S_1&S_2&z\\\hline 1&5&1&0&0&1\\7&0&0&1&0&1\\\hline -1&-1&0&0&1&0\end{array}
$$
$$
\begin{array}{c}y_1+y_2=z\\ -y_1-y_2+z=0\end{array}
$$
![[Discrete_Mathematics/images/Pasted_image_20240501102131.png|500]]
$$
\begin{array}{c}y_1+5y_2\le 1\\ 7y_1\le 1\end{array}
$$

**Part (b) (iii)**
We have to write the ratios
$$
\begin{array}{cccc|c|cc}y_1&y_2&S_1&S_2&z&&\text{ratio}\\\hline 1&5&1&0&0&1&1/1\\7&0&0&1&0&1&1/7\\\hline -1&-1&0&0&1&0\end{array}
$$
Doing the row operations
$$
\begin{array}{c}R_1\mapsto R_1-\frac{1}7 R_2\\ R_2\mapsto \frac{1}{7} R_2\\R_3\mapsto R_3+\frac{1}7 R_2\end{array}\,\,\,\,\,\,\,\,\,\begin{array}{cccc|c|c}y_1&y_2&S_1&S_2\\\hline 0&5&1&-1/7&0&6/7\\1&0&0&1/7&0&1/7\\\hline 0&-1&0&1/7&1&1/7\end{array}
$$
What we are trying to do is $Ax=b$, but we can split it up into $Bx_B+Nx_N$ and set the second term to zero.
$$
\begin{array}{c}R_1\mapsto \frac{1}5 R_1\\R_2\mapsto R_2\\ R_3\mapsto R_3+\frac{1}5 R_1\end{array}\,\,\,\,\,\,\,\,\,\,\begin{array}{cccc|c}y_1&y_2&S_1&S_2&\\\hline 0&1&1/5&-1/35&6/35\\1&0&0&1/7&1/7\\\hline 0&0&1/5&4/35&11/35\end{array}
$$
We have nothing non-negative in the bottom row, and we can see that $\frac{1}5+\frac{4}{35}=\frac{11}{35}$ and $\frac{6}{35}+\frac{1}7=\frac{11}{35}$

![[Discrete_Mathematics/images/Pasted_image_20240501103746.png|500]]

**Part (b) (iv)**
The optimal strategy
$$
\begin{array}{c}y_1=\frac{1}{7}\\y_2=\frac{6}{35}\end{array}\,\,\,\,\,\,\,\,\bar q=\frac{35}{11}\times\begin{pmatrix}1/7\\6/35\end{pmatrix}=\begin{pmatrix}5/11\\6/11\end{pmatrix}
$$
$$
\begin{array}{c}x_1=\frac{1}5\\x_2=\frac{4}{35}\end{array}\,\,\,\,\,\,\,\,\,\, \bar p=\frac{35}{11}\times\begin{pmatrix}1/5\\4/35\end{pmatrix}=\begin{pmatrix}7/11\\4/11\end{pmatrix}
$$
![[Discrete_Mathematics/images/Pasted_image_20240501104156.png]]

**Part (c) (i)**
$$
\begin{array}{c|c}\text{Player B action}&\text{Payoff to Player A}\\\hline C_1&-p+4(1-p)=4-5p\\C_2&-3p+3(1-p)=3-6p\\C_3&p-4(1-p)=-4+5p\end{array}
$$
$$
\text{Total expected payoff}=q_1(4-5p)+q_2(3-6p)+q_3(-4+5p)
$$
![[Discrete_Mathematics/images/Pasted_image_20240501104809.png]]

**Part (c) (ii)**
$$
\begin{array}{cc}C_1:4-5p&p=0\,\,\,\, f(p)-4\,\,\,\,\, f(p)=0\,\,\,\,\,p=4/5\\ C_2: 3-6p&p=0\,\,\,\, f(p)=3\,\,\,\,\, f(p)=0\,\,\,\,\, p=1/2\\C_3:-4+5p&p=0\,\,\,\, f(p)=-4\,\,\,\,\, f(p)=0\,\,\,\,\,p=4/5\end{array}
$$
![[Discrete_Mathematics/images/Pasted_image_20240501105424.png|300]]



