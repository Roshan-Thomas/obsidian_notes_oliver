---
title: Lecture 3
date: 02 Feb 2024
---
# Separation of Variables
- We can use separation of variables to solve parabolic, hyperbolic, or elliptic PDEs too.
- We need a pair of homogenous boundary conditions (not a strict requirement).

Note: When solving the heat equation, the results that you get should match the expectation you have of a system having heat and it dissipating.

The solution of the heat equation

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240203012246.png]]

The initial conditions does not match the boundary conditions. So the derivative is not continuous.

## Laplace Equation
$$
u_{xx}+u_{yy}=0
$$

We contrate on the simple case of a rectangular domain in 2D

In this problem we focus on three homogenous boundary conditions, and one non-homogenous boundary condition.

### Example 5.2
Solve Laplace equation on a rectangular domain subject to the Dirichlet boundary conditions 
$$
u(0,y)=u(L,y)=0\,\,\,\,\,\, u(x,0)=0,\, u(x,M)=f(x)
$$
for the particular case $L=4$ and $M=2$ and 
$$
f(x)=\sin\left(\frac{\pi x}4\right)-\frac 1 9\sin\left(\frac{3\pi x}4\right)
$$

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240203012916.png]]

We are looking for a separable solution, so that $u(x,y)=X(x)Y(y)$

**First Step**
$$
X''(x)Y(y)+X(x)Y''(y)=0
$$
Dividing by $XY$
$$
\frac{X''(x)}{X(x)}+\frac{Y''(y)}{Y(y)}=0
$$
$$
\frac{X''(x)}{X(x)}=-\frac{Y''(y)}{Y(y)}=u\,\,\,\,\text{constant}
$$
Note: Make sure the X's are on one side and the Y's are on the other side.

**Step 2: Decide the sign of $u$**
$$
a)\,\, u>0,\,\,\, u=k^2,\,\,\,\,k>0
$$
$$
\begin{rcases}X''=kx\\ Y''=-k^2Y\end{rcases}\,\,\, \begin{array}{c}X(x)=Ae^{kx}+Be^{-kx}\\ Y(y)=C\cos ky+D\sin ky\end{array}
$$
This is not a good solution, as the boundary conditions are not satisfied as its a linearly independent set of equations

$$
b)\,\, u<0,\,\,\,\,\,\, u=-k^2
$$
$$
\begin{rcases}X''=-k^2Y\\ Y''=k^2Y\end{rcases}\,\,\,\,\,\begin{array}{c}X(x)=A\cos kx+B\sin kx\\ Y(y)=Ce^{ky}+De^{-ky}\end{array}
$$
**Step 3: Apply homogenous conditions**
$$
0=X(0)=A+B\cdot 0=A\Rightarrow X(x)=B\sin(kx)
$$
$$
0=X(L)=B\sin kL\Rightarrow \sin kL=0\Rightarrow kL=n\pi,\,\,n\in Z
$$

Clearly, $k=n\pi/L$
$$
X(x)=B\sin\left(\frac{n\pi x}L\right)
$$

The other boundary condition (bottom)
$$
0=Y(0)=C\cdot 1+D\cdot 1\Rightarrow D=-C
$$
$$
Y(y)=C(e^{ky}-e^{-ky})=\sinh(ky)2\cdot c
$$
$$
Y(y)=2c\sinh\left(\frac{n\pi y}L\right)
$$
**Step 4: Bringing everything together**
$$
\begin{split}u(x,y)=&\sum_{n=1}^\infty X_n(x)Y_n(y)\\ =&\sum_{n=1}^\infty \beta_n\sin\left(\frac{n\pi x}L\right)\sinh\left(\frac{n\pi y}L\right)\end{split}
$$

**Step 5: Find $\beta_n$ from inhomogeneous boundary conditions**
$$
y=M:\, u=f(x),\,\,\,\, L=4,\, M=2
$$
$$
f(x)=\sin\frac{\pi x}4-\frac 1 9 \sin\left(\frac{3\pi x}4\right)
$$
$$
\begin{split}f(x)&=\sum_{n=1}^\infty \beta_n\sin\left(\frac{n\pi x}4\right)\sinh\left(\frac{n\pi\cdot 2}4\right)\\ &=\sum_{n=1}^\infty b_n\sin\left(\frac{n\pi x}4\right)\end{split}
$$
We choose $b_1=1$, and $b_3=-\frac{1}9$
$$
b_n=0\text{ for }n\ne 1 \text{ and }n\ne 3
$$
$$
b_n=\beta_n\sinh\left(\frac{n\pi}2\right)\Rightarrow \beta_n=\frac{b_n}{\sinh\frac{n\pi}2}\tag{DONE}
$$
The solution

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240203015157.png]]




