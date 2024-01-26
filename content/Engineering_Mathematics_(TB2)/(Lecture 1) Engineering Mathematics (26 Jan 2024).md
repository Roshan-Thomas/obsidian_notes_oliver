---
title: Lecture 1
date: 26 Jan 2024
---
## Linearity
$$
f:\Re^n\rightarrow \Re^n
$$
Linear homogenous if $\forall x_{11}x_2\in \Re^n,\,\,\lambda\in\Re$ 
1. $f(x_1+x_2)=f(x_1)+f(x_2)$
2. $f(\lambda x_1)=\lambda f(x_1)$
**OR**
$$
grad \,f(0)\cdot x=f(x) 
$$
___
$f$ is linear if 
$$
g(x)=f(x)-f(0)
$$
and $g(x)$ is linear homogenous, then $f$ is linear.

if $f(0)=0\Rightarrow$ homogenous
___
$$
u_x=\frac{\partial u}{\partial x},\,\,\,\,\, u_{xx}=\frac{\partial^2 u }{\partial x^2},\,\,\,\, u_{xy}=\frac{\partial^2 u}{\partial x\partial y}
$$
$$
f(u_{xx}, u_{xy}, u_{yy}, u_x, u_y, u, x, y)=0
$$
$$
f(0,0,0,0,0,0,x, y)\begin{cases}\text{if }=0&\text{homogenous}\\\text{if }\ne 0&\text{inhomogenous}\end{cases}
$$
___
$$
(u_{xx})^2+2u_{xy}+\sin xy=0\tag{inhomogenous equation}
$$
$$
(2u_{xx}, 2, 0)\cdot (u_{xx}, u_{xy}, u_{yy})\stackrel{?}{=}(u_{xx})^2+2u_{xy}
$$
$$
2(u_{xx})^2+2u_{xy}\ne
$$
So, its non-linear

This method is a fool-proof way of making sure a function is linear or not
___
# Introduction to PDEs
#### Worked Example 4.2
$$
A\frac{\partial^2 u}{\partial x^2}+B\frac{\partial^2 u}{\partial y^2}+C\frac{\partial^2 u}{\partial y^2}=f(x,y,u,u_x, u_y)
$$
$$
D=B^2-4AC=\begin{cases}>0&\text{hyperbolic}\\=0&\text{parabolic PDE}\\<0&\text{elliptic}\end{cases}
$$
The canonical form
$$
D>0:u_{xy}+\dots=0
$$
$$
D=0:u_{xx}+\dots=0
$$
$$
D<0: u_{xx}+u_{yy}+\dots=0
$$
____
1. $u_t=d^2 u_{xx}$ (The heat equation)
$t\rightarrow y$
$$
u_y=d^2 u_{xx}
$$
$$
A=\alpha^2,\,\,\,B=0,\,\,\,\, C=0
$$
$$
D=B^2-4AC=0^2-4\alpha^2\cdot 0=0\tag{Parabolic}
$$
2. $u_{tt}=C^2 u_{xx}$
we label $t\rightarrow y$
$$
u_{yy}=C^2u_{xx}
$$
$$
C^2u_{xx}-u_{yy}=0
$$
$$
A=C^2,\,\,\,\, B=0,\,\,\,\, C=-1
$$
$$
D=B^2-4AC=0^2-4C^2(-1)=4C^2
$$
3. $u_{xx}+u_{yy}=0$ (Laplace equation)
$$
A=1,\,\,\,\,\, B=0,\,\,\,\,\, C=1
$$
$$
D=B^2-4AC=0^2-4\cdot 1\cdot 1=-4<0\tag{elliptic}
$$
4. $u_{xx}-3u_{xy}+u_{yy}=0$
$$
A=1,\,\,\,\, B=-3,\,\,\,\,\, C=1
$$
$$
D=B^2-4AC=(-3)^2-4\cdot 1\cdot 1=9-4=5>0\tag{hyperbolic}
$$
5. $(1-M^2)u_{xx}+u_{yy}=0$ (This equation describes the airflow around a tin foil described by the Mach number M)
$$
A=1-M^2,\,\,\,\,\,\, B=0,\,\,\,\, C=1
$$
$$
D=B^2-4AC=0^2-4(1-M^2)\cdot 1=4(M^2-1)
$$
So, the equation is
$$
\begin{cases}>0&\text{hyperbolic if }M^2-1>0\text{ or }M^2>1\\ =0&\text{parabolic if }M^2-1=0\text{ or }M^2=1\\ <0&\text{elliptic if }M^2-1<0\text{ or }M^2<1\end{cases}
$$
6. $u_{xx}=xu_{yy}$
$$
u_{xx}-xu_{yy}=0
$$
$$
A=1,\,\,\,\,\, B=0,\,\,\,\,\, C=-X
$$
$$
D=B^2-4AC=0^2-4\cdot 1(-x)=4x
$$
$$
\begin{cases}>0&\text{if }x>0&\text{hyperbolic}\\=0&\text{if }x=0&\text{parabolic}\\<0&\text{ if }x<0&\text{elliptic}\end{cases}
$$
___
## Parabolic PDEs
- They are quite nice, because they smooth things out, and evens out across a surface and reaches equilibrium
	- Example: heat equation
To solve them, we need:
- A single initial condition
- a pair of boundary conditions
- and can be solved in an unbounded domain (over an infinite timeline)
## Hyperbolic PDEs
- Information travels in a finite speed, and all solutions travel without decay.
	- Example: wave equation
To solve them, we need:
- two initial conditions at a given time
- a pair of boundary conditions
- can be solved in an unbounded domain
## Elliptic PDEs
- Describes things at rest or at equilibrium, and there is no 'time-like' direction
	- Example: Laplace equation
To solve them, we need:
- a closed domain
- a single condition at every point on the boundary
