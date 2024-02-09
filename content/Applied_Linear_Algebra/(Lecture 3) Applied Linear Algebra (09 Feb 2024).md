---
title: Lecture 3
date: 09 Feb 2024
---
# Vector Spaces
$$
\{1,c,2x^2-1,x^2+1\}
$$
$$
c_0(1)+c_1(x)+c_2(2x^2-1)+c_3(x^2+1)=a_2x^2+a_1x+a_0
$$
Has Solutions $\rightarrow$ these span $P^2$

Are these linearly independent?
$$
c_0(1)+c_1(x)+c_2(2x^2-1)+c_3(x^2+1)=0
$$
$$
\begin{split}c_0-c_2+c_3&=0\\ c_1&=0\\ 2c_2+c_3&=0\end{split}
$$
$$
\begin{array}{c}c_3=1\\ c_2=-\frac{1}2 \\ c_0=-\frac 1 2\end{array}
$$
**NOT** linearly independent
___

Consider another case
$$
\{1,x,2x^2-1\}
$$
$$
c_0(1)+c_1(x)+c_2(2x^2-1)=0
$$
$$
\begin{split}1: c_0-c_2&=0\\ x: c_1&=0\\ x^2: 2c_2&=0\end{split}
$$
$$
\begin{array}{c}c_1=0\\c_2=0\\c_0=0\end{array}
$$
**Linear Independence** ✅
____
# Basis
A *basis* is a linearly independent spanning set.
- Basis are not unique

We have shown that $\{1,x,2x^2-1\}$ is linearly independent, and we have also shown that it is spanning, and now we can show that it is a basis for $P^2$
$$
P^2:\,\,\{1,x,x^2\}
$$
**Example**
$$
p(x)=4x^2+5x-7
$$
$$
c_0(1)+c_1(x)+c_2(2x^2-1)=4x^2+5x-7
$$
Demonstrating as before,
$$
\begin{split}1:\,&c_0-c_2=-7\\x:\,&c_1=5\\x^2:\,&2c_2=4\end{split}
$$
$$
\begin{array}{c}c_2=2\\c_1=5\\c_0-2=-7\\c_0=-5\end{array}
$$
$$
p(x)=-5(1)+5(x)+2(2x^2-1)
$$
____
Lets take a differential equation
$$
\ddot x-2\dot x+x=0
$$
To solve this equation, we set up an auxiliary equation
$$
x=e^{mt}\,\,\,\,\,\,\,\,\, \begin{split}m^2-2m+1=&0\\(m-1)^2=&0\\m=&1\end{split}
$$
$$
x_1=e^t\,\,\,\,\,\,\, x_2=te^t
$$
The reason why we have a $t$ in the second $x$ i.e. $x_2$ is cause we need a linearly independent solution. 

With this, we have found a basis for the vector space of solutions to this ODE.

If $x_1$ and $x_2$ are solutions, then $x_1+x_2$ is also a solution (by the superposition principle)

$x_1$ is a solution $\Rightarrow$ $\lambda x_1$
# Inner Products and Norms
You should be able to show three properties to satisfy an *inner product*
- Linearity
$$
\langle x+y,z\rangle=\langle x,z\rangle+\langle y+z\rangle
$$
$$
\langle \lambda x,z\rangle=\lambda\langle x,z\rangle
$$
- Symmetry
$$
\langle x,y\rangle=\langle y,x\rangle
$$
- Positivity
$$
\langle x, x\rangle\ge 0
$$
$$
\langle x,x\rangle =0\Leftrightarrow x=0
$$
The properties for a *Norm*
- Homogeneity
$$
||c\bar v||=|c|\,\,\vert\vert\bar v\vert\vert
$$
- Positivity
$$
||\bar v||\ge 0\,\,\,\,\,\,\,\, ||\bar v||=0\Leftrightarrow \bar v=0
$$
- Triangle inequality
$$
||\bar v+\bar w||\le||\bar v||+||\bar w||
$$
Triangle Inequality tells us that the sum of two sides of a triangle is always greater than or equal to the third side of the triangle.

### Theorem
If $\langle \cdot,\cdot\rangle$ is an inner product on a vector space $V$, then $\forall\vec v\in V$, $||\vec v||=\left(\langle\vec v,\vec v\rangle\right)^{\frac 1 2}$ is a norm.

**Step 1:** Show homogeneity
$$
\begin{split}||c\vec v||^2&=\langle c\vec v,c\vec v\rangle\,\,\,\,\text{by definition}\\ &=c\langle\vec v,c\vec v\rangle\,\,\,\,\text{linearity}\\&=c\langle c\vec v,\vec v\rangle\,\,\,\,\,\text{symmetry}\\&=c^2\langle\vec v,\vec v\rangle\,\,\,\,\text{linearity}\\&=c^2||\vec v||\,\,\,\,\,\text{definition}\\ ||c\vec v||&=|c|\,\,||\vec v||\end{split}
$$

**Step 2:** Show Positivity
$$
\begin{split}||\vec v||^2&=\langle\vec v,\vec v\rangle\ge 0\,\,\,\,\text{by the properties of the inner product}\end{split}
$$
$$
\begin{split}||\vec v||^2=0&\\ &\langle\vec v,\vec v\rangle=0\,\,\Leftrightarrow\vec v=0\,\,\text{by the def. of an inner product}\end{split}
$$
**Step 3:** Show Triangle Inequality 
- From the videos, the Chauchy-Sharwtz inequality $\langle \vec v,\vec w\rangle\le||\vec v||\,\,||\vec v||$ 

$$
\begin{split}||\vec v+\vec w||^2&=\langle\vec v+\vec w,\vec v+\vec w\rangle\\&=\langle \vec v,\vec v+\vec w\rangle+\langle\vec w,\vec v+\vec w\rangle\\&=\langle\vec v+\vec w,\vec v\rangle+\langle\vec v+\vec w,\vec w\rangle\\&=\langle\vec v,\vec v\rangle+\langle\vec v,w\rangle+\langle\vec w,\vec v\rangle+\langle\vec w,\vec w\rangle\\&=||\vec v||^2+2\langle\vec v,\vec w\rangle+||\vec w||^2\\&\le ||\vec v||^2+2||\vec v||\,\,||\vec w||+||\vec w||^2\,\,\,\,\text{By CS inequality}\\&=\left(||\vec v||+||\vec w||\right)^2\end{split}
$$
QED $\square$
___
$V$ - vector space of linear functions $P^{(1)}$
$$
V=\text{span}\{1,t\}
$$
We are going to show that an inner products with two linear functions when integrated is an inner product
$$
\langle x(t),y(t)\rangle=\int_0^1 x(t)y(t)\, dt\,\,\,\,\,\text{ is an inner product}
$$
**Step 1:** Show linearity
$$
x,y,z\in V
$$
$$
\begin{split}\langle x+y,z\rangle&=\int_0^1(x+y)z\, dt=\int_0^1 xz+yz\, dt\\ &=\int_0^1 xz\, dt+\int_0^1 yz\, dt\\&=\langle x,z\rangle+\langle y,z\rangle\end{split}
$$
$\lambda\in R$
$$
\langle\lambda x,y\rangle=\int_0^1\lambda xy\, dt=\lambda\int_0^1 xy\, dt=\lambda\langle x,y\rangle
$$
Thus it is linear.

**Step 2:** Show symmetry
$$
\langle x,y\rangle=\int_0^1 xy\, dt=\int_0^1 yx\, dt=\langle y,x\rangle
$$
Thus it is symmetrical.

**Step 3:** Show positivity
$$
\langle\vec x,\vec x\rangle=\int_0^1 xx\, dt=\int_0^1(at+b)^2\, dt
$$
The element $(at+b)^2$ is non-negative meaning it is $\ge 0$

So you are integrating a function that is only above the $t$ axis. The area is going to be positive.
$$
\int_0^1(at+b)^2\, dt\ge 0
$$
It will only integrate to zero if the function itself is $0$. 
So,
$$
\int_0^1(at+b)^2\, dt=0\,\,\Leftrightarrow \begin{array}{c}(at+b)^2=0\\ at+b=x=0\end{array}
$$
Thus we have shown positivity.
