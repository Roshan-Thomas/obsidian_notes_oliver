---
title: Lecture 2
date: 02 Feb 2024
---
### Recap: 
**Solvability**
$$
\begin{array}{c}x+2ay=a^2\\ ax+ay=a^3+1\end{array}
$$
$$
\left[\begin{array}{cc|c}1&2a&a^2\\ a&a&a^3+1\end{array}\right]
$$
$R_2\mapsto R_2-aR_1$
$$
\left[\begin{array}{cc|c}1&2a&a^2\\ 0&a-2a^2&1\end{array}\right]
$$
$a-2a^2\ne0$ $\rightarrow$ full rank $\Rightarrow$ unique solution
$a-2a^2=0\rightarrow$ Inconsistent $\Rightarrow$ no solutions

Lets take another similar case
$$
\begin{array}{c}x+2ay=a^2\\ax+ay=a^3\end{array}
$$
$R_2\mapsto R_2-aR_1$
$$
\left[\begin{array}{cc|c}1&2a&a^2\\ 0&a-2a^2&0\end{array}\right]
$$
$a-2a^2\ne0\rightarrow$ full rank $\Rightarrow$ unique solution
$a-2a^2=0\rightarrow$ consistent $\rightarrow$ rank = 1 $\Rightarrow$ infinite solutions. $(0x+0y=0)$
___
# Vector spaces and subspaces
To define a vector space we need two vectors 

The two operations are:
1. Vector addition $v+w\in V$
2. Scalar Multiplication $cv\in V$

A *subspace* is a subset of the vector space $V$ that is itself a vector space under the same operations and the same zero element.
	It is basically a smaller vector space within your original vector space $V$.

### **Examples of Vector Space**s
- $R^n$
	- $R^3$ (3 Dimensional space)
		- subspaces?
			- any lower dimensional spaces that contain the origin

- $C\left([0,1]\right)$ - $\{f:[0,1]\rightarrow R:\text{ f is continuous}\}$
	- $e(x)=0$ $\leftarrow$ additive identity
$$
\text{if }f\in C([0,1]),\,\,\,\,\,\,\, g\in C([0,1])
$$
$$
\begin{array}{c}f+g\text{ is also continouous }f+g\in C([0,1])\\ \lambda f\text{ is just a vertical stretch }\lambda f\in C([0,1])\end{array}
$$
$$
\begin{split}\text{Subspace?} &\\ & V=\{f\in C([0,1]): f(0)=0\}\\ &P^n - \text{ polynomials of order at most n.}\\ & \text{From videos $P^n$ is a vector space, and polynomials are clearly continuous}\\ & P^n\in C([0,1]) \end{split}
$$

- Sequences: $R^\infty=\{(x_1,x_2,\dots): x_i\in R\}$
$$
\begin{array}{c}\bar x=(x_1,x_2,\dots)\\ \bar y=(y_1,y_2,\dots)\\ \text{By additive identity } \bar 0=(0,0,\dots)\\ \bar x+\bar y=(x_1+y_1,x_2+y_2,\dots)\in R^\infty \\ \lambda\bar x=(\lambda x_1,\lambda x_2,\dots)\in R^\infty\end{array}
$$
Interesting subspace is *all Fibonacci sequences* $(x_{n+2}=x_{n+1}+x_n)$

Showing that the Fibonacci sequence holds the additive identity
$$
\bar 0=(0,0,\dots) \text{ is a Fibonacci sequence}
$$
$$
\begin{split} \bar x=(x_1,x_2)&\\ \bar y=(y_1,y_2,\dots)&\\ \bar z=\bar x+\bar y = (z_1,z_2,\dots)&\\ z_{n+2}&= x_{n+2}+y_{n+2}\\ &=x_{n+1}+x_n + y_{n+1}+y_n\\ &=x_{x+1}+y_{n+1}+x_n+y_n\\&=z_{n+1}+z_n\Rightarrow \bar z\text{ is Fibonacci}\\ \lambda\bar x=(\lambda x_1,\lambda x_2,\dots)&\\ \lambda x_{n+2}&=\lambda(x_{n+1}+x_n)\\ &=\lambda x_{n+1}+\lambda x_n\rightarrow \lambda \bar x \text{ is Fibonacci} \end{split}
$$
# Span
Span is a set of all linear combinations $v_1,\dots, v_k$

Example: $R^2$ 
$$
\text{Position }\binom{5}{3}=5\bar i+3\bar j
$$
$$
\text{Span }\{\bar i,\bar j\}=R^2
$$


Consider two vector spaces
$$
U=\text{span }\left\{\begin{bmatrix}2\\5\\0\end{bmatrix},\begin{bmatrix}3\\2\\1\end{bmatrix}\right\}
$$
$$
V=\text{span }\left\{\begin{bmatrix}5\\7\\1\end{bmatrix},\begin{bmatrix}1\\-3\\1\end{bmatrix}\right\}
$$
Is V a subspace of U?
Is U a subspace of V?

For $u$ to be in the span of $U$
$$
\bar u\in U\,\,\,\,\,\,\,\, \bar u=a_1\bar u_1+a_2\bar u_2
$$
$$
\bar v\in V\,\,\,\,\,\,\,\, \bar v=b_1\bar v_1+b_2\bar v_2
$$
If $v\in U$
$$
\bar v_1=a_1\bar u_1+a_2\bar u_2
$$
$$
\begin{bmatrix}2&3\\5&2\\0&1\end{bmatrix}\begin{bmatrix}a_1\\a_2\end{bmatrix}=\begin{bmatrix}5\\7\\1\end{bmatrix}
$$
$$
\left[\begin{array}{cc|c}2&3&5\\5&2&7\\ 0&1&1\end{array}\right]
$$
$$
\begin{array}{c}a_2=1\\a_1=1\end{array}
$$
$\bar v_1=\bar u_1+\bar u_2$

$\bar v_2=a_1\bar u_1+a_2\bar u_2$
$$
\left[\begin{array}{cc|c}2&3&1\\5&2&-3\\0&1&1\end{array}\right]
$$
$$
\begin{array}{c}a_2=1\\ 5a_1+2=-3\Rightarrow a_1=-1\\ 2a_1+3a_2=-2+3=1=RHS\end{array}
$$

$\bar v_2=-\bar u_1+\bar u_2$

$$
\begin{split} \bar v=b_1\bar u_1+b_2\bar v_2&=b_1(\bar u_1+\bar u_2)+b_2(-\bar u_1+\bar u_2)\\&=\bar u_1(b_1-b_2)+\bar u_2(b_1+b_2)\in U\\& V\subset U\end{split}
$$

If $u\in V$
$$
\begin{split}\bar u_1=&b_1\bar v_1+b_2\bar v_2\\ &\rightarrow \bar u_1=\frac{1}2 \bar v_1-\frac 12 \bar v_2\end{split}
$$
$$
\begin{split}\bar u_2&=b_1\bar v_1+b_2\bar v_2\\ &=\frac{1}2 \bar v_1+\frac 12 \bar v_2\end{split}
$$
$$
\begin{split}\bar u&=a_1\bar u_1+\bar a_2\bar u_2\\ &=a_1\left(\frac 1 2 \bar v_1-\frac 1 2 \bar v_2\right)+a_2\left(\frac 1 2 \bar v_1+\bar v_2\right)\\&=\left(\frac 1 2 a_1+\frac 1 2 a_2\right)\bar u_1+\left(-\frac 1 2 a_1+\frac 1 2 a_2\right)\bar u_2\end{split}
$$

Thus 
$$
\bar u\in V\,\,\,\,\,\,\,\,\, u\subset V
$$
$$
U=V
$$
____
A set of polynomials $\{1,x,2x^2-1,x^2+1\}$
Questions:
1. Do they span $P^2$?
2. Are they linearly independent?

A polynomial in $P^2$        $a_2x^2+a_1x+a_0$
If it spans it, then 
$$
a_2x^2+a_1x+a_0=c_0\times 1+c_1x+c_2(2x^2-1)+c_3(x^2+1)
$$
Is this possible?

Regrouping the elements
$$
\begin{split}&=c_0-c_2+c_3+c_1x+(2c_2+c_3)x^2\end{split}
$$
$$
\begin{array}{c}c_0-c_2+c_3=a_0\\ c_1=a_1\\ 2c_2+c_3=a_2\end{array}\left[\begin{array}{cccc|c}1&0&-1&1&a_0\\ 0&1&0&0&a_1\\ 0&0&2&1&a_2\end{array}\right]
$$
- Rank 3 (< 4)
- Last row $\rightarrow$ consistent
	- Infinite solutions

So, $\{1,x,2x^2-1,x^2+1\}$ spans $P^2$

