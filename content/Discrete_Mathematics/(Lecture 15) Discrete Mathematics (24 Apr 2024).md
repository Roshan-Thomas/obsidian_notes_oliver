---
title: Lecture 15
date: 24 Apr 2024
---
The story so far on **zero-sum games**
$$
\bar R=\text{payoff matrix for player A (we want it to be all non-negative)}
$$
$$
v=\text{value of game to A (positive)}
$$
We want to choose $\bar p, \bar q$ so that
- $\bar p$ is chosen to maximize $v=\bar p^T\bar R\bar q$
- $\bar q$ is chosen to maximize $v=\bar p^T\bar R\bar q$

The constraints were $\bar 1\cdot\bar p=\bar 1\cdot \bar q=1$

Introduced rescaled variables
$$
\begin{array}{c}\frac{\bar p}{v}=\bar x\\ \frac{\bar q}{v}=\bar y\end{array}
$$
Linear programming for $\bar y$
- Maximize $\bar 1\cdot\bar y=1/v$ subject to $\bar y\ge 0$ elementwise.

Our payoff matrix was
$$
\bar R=\begin{pmatrix}2&4\\3&1\end{pmatrix}
$$
We want to maximize
$$
y_1+y_2=\overbrace{\frac 1 v}^w
$$
Subject to
$$
\left.\begin{array}{c}y_1\ge0\\y_2\ge 0\end{array}\right]\, \bar y\ge 0
$$
$$
\left.\begin{array}{c}2y_1+4y_2\le 1\\3y_1+y_2\le 1\end{array}\right]\,\bar R\bar y\le 1
$$
![[Discrete_Mathematics/images/Pasted_image_20240424101652.png|500]]

# Simplex method
Introduced slack variables to make the inequalities into equations.

2 inequalities $\implies$ I need 2 slack variables 
- Side Note: the No. of inequalities $=$ No. of actions for Player A $=$ No. of slack variables

$$
\begin{array}{ccccc}2y_1&+4y_2&+s_1&&=1\\3y_1&+y_2&&+s_2&=1\end{array}\,\,\,\,\,\,\,\,\begin{array}{c}s_1\le 0\\s_2\le 0\end{array}
$$

I want to maximize $w=y_1+y_2$
I write this as
$$
-y_1-y_2+w=0
$$
Writing this in matrix form 
$$
\begin{array}{ccccc}2y_1&+4y_2&+s_1&&&=1\\3y_1&+y_2&&+s_2&&=1\\-y_1&-y_2&&&+w&=0\end{array}
$$
$$
\begin{pmatrix}2&4&1&0&0\\3&1&0&1&0\\-1&-1&0&0&1\end{pmatrix}\begin{pmatrix}y_1\\y_2\\s_1\\s_2\\w\end{pmatrix}=\begin{pmatrix}1\\1\\0\end{pmatrix}
$$
If we set $y_1, y_2$ to be zero since they don't have an identity column, we can read the second matrix as 
$$
\begin{pmatrix}0\\0\\1\\1\\0\end{pmatrix}
$$
On a graph, only the corners are important points when it comes to maximization problems. 

![[Discrete_Mathematics/images/Pasted_image_20240424102721.png|400]]
$$
\begin{array}{c}s_1=1\,\,\,s_2=1\\y_1=y_2=0\end{array}
$$
The initial Tableau,
$$
\begin{array}{ccccc|c}2&4&1&0&0&1\\3&1&0&1&0&1\\\hline-1&-1&0&0&1&0\end{array}
$$
Useful things in the Tableau are 
$$
\overbrace{\begin{array}{ccccc|c}2&4&1&0&0&1\\3&1&0&1&0&1\\\hline-1&-1&0&0&1&0\end{array}}^{\begin{array}{cccccc}y_1&&y_2&&s_1&&s_2&&w&\end{array}}
$$
Duality: values in bottom row beneath the slack variables tell you about Player A.

**Checks:** We know that $y_1,\,y_2,\,s_1,\,s_2,\,x_1,\,x_2,\,w$ must all be non-negative.

We know that
$$
\begin{array}{c}y_1+y_2=w\\x_1+x_2=w\end{array}
$$
Reading off the matrix
$$
\begin{array}{c}s_1=1&s_2=1&y_1=0&y_2=0&x_1=0&x_2=0&w=0\end{array}
$$
**Row Operations**
Pick the most negative value on the bottom row
- Interpretation: which variable out of our $y$'s and $s$'s has the biggest impact on $w$
- Find the smallest positive value of the RHS Value divided by the value that is in that column.
	- That will tell us the first constraint we come across, and is known as the pivot row
- Rescale pivot rows, do row operations as usual. Check, interpret, repeat!

$$
\begin{array}{ccccc|c}2&4&1&0&0&1\\3&1&0&1&0&1\\\hline-1&-1&0&0&1&0\end{array}\,\,\,\,\,\begin{array}{c}\frac 1 2\text{ ratio}\\\frac 1 3\text{ ratio}\\\end{array}
$$
Pick the furthest left row as pivot column

Smallest ratio $=\frac 1 3$

First constraint I hit is the $s_2$ constraint.
$$
\begin{array}{ccccc|c}2&4&1&0&0&1\\1&\frac{1}3&0&\frac 1 3&0&\frac 1 3\\\hline -1&-1&0&0&1&0\end{array}\,\,\begin{array}{c}\\ R_2/3\\ \end{array}
$$
$R_2/3$ to rescale to get 1 in the pivot column
$$
\begin{array}{ccccc|c}0&\frac{10}3&1&\frac{-2}3&0&\frac{1}3\\1&\frac 1 3&0&\frac 13&0&\frac 1 3\\\hline 0&\frac{-2}3&0&\frac 1 3&1&\frac{1}3\end{array}\,\,\,\,\begin{array}{c}R_1-2R_2\\ \\R_3+R_2\end{array}
$$
Identify the columns, set $y_2$ and $s_2$ to be zero
$$
\begin{array}{c}s_1=\frac 1 3\,\,\,\text{ from top row}\\ y_1=\frac{1}3\,\,\,\text{ from mid row}\end{array}
$$
$$
\left.\begin{array}{c}x_1=0\\x_2=\frac 1 3\end{array}\right]\text{ duality}\,\,\,\,\,\,\,\,\,\,\,w=\frac 1 3\,\,\,\,\,\,\therefore \text{ Pass}
$$
*Question*: Do I have negative values in bottom row?
- Yes, So I have to keep going.

$$
\begin{array}{ccccc|c}0&\frac{10}3&1&\frac{-2}3&0&\frac 1 3\\1&\frac 1 3&0&\frac 1 3&0&\frac 1 3\\\hline 0&\frac{-2}3&0&\frac 1 3&1&\frac 1 3\end{array}\,\,\,\begin{array}{c}\frac 1 {10}\\1 \\ \end{array}
$$
$$
\begin{array}{ccccc|c}0&1&\frac 3{10}&\frac{-1}5&0&\frac{1}{10}\\1&0&\frac{1}{10}&\frac{2}{5}&0&\frac{3}{10}\\0&0&\frac{1}5&\frac{1}5& 1&\frac{2}5\end{array}\,\,\,\,\begin{array}{cc}R_1\times \frac{3}{10}\\R_2-\frac 1 3&\text{rescaled }R_1\\R_3+\frac{2}3&\text{rescaled }R_1\end{array}
$$
$$
\begin{array}{c}y_2=\frac{1}{10}\\y_1=\frac{3}{10}\end{array}\,\,\,\,\,\, s_1=s_2=0
$$
$$
x_1=x_2=\frac 1 5\,\,\,\,\,\,\, w=\frac 2 5
$$
At optimum, $w=\frac 2 5$
$$
\bar y=\begin{pmatrix}\frac{1}{10}\\\frac{3}{10}\end{pmatrix}\,\,\,\,\bar x=\begin{pmatrix}\frac 1 5\\\frac 1 5\end{pmatrix}
$$
$v=\frac{5}2$
Expected return $=2\frac{1}2$

Nash equilibrium 
$$
\bar p=\begin{pmatrix}\frac{1}2\\\frac 1 2\end{pmatrix}\,\,\,\,\,\,\bar q=\begin{pmatrix}\frac 1 4\\\frac 3 4\end{pmatrix}
$$
