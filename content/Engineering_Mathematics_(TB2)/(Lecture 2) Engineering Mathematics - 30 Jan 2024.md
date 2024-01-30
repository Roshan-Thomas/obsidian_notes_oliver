---
title: Lecture 2
date: 30 Jan 2024
---
PDE - Partial Differential Equations
# Separation of Variables
It is an analytical technique to solve PDEs. 
- It is done by separating the variables of the PDE, making it into an ODE.
- Fourier series is used as part of this method.
- Solution process for wave, heat and Laplace equations.

## Wave Equation
Consider the wave equation on the finite domain

**Notation**: $u_{tt}$ indicates the second derivative 
$$
u_{tt}=c^2 u_{xx}\,\,\,\, ; \,\,\,\,\,\, 0\le x\le L,\,\,\,\, t\ge 0
$$
Boundary condition: $u(0,t)=u(L,t)=0$
Initial condition: $u(x,0)=f(x)$ and $u_t(x,0)=0$

Assume a separable solution
$$
u(x,t)=X(x)T(t)\,\,\,\,\,\,\,\,\,\,\, N.B.\, u(x,t)=\sum_n X_n(x)T_n(t)
$$
Substitute into the PDE
$$
X(x)T''(t)=c^2 X''(x)T(t)
$$
Rearranging the terms:
$$
\frac{1}{c^2}\frac{T''(t)}{T(t)}=\frac{X''(x)}{X(x)}=\mu \in \Re
$$
Hence we have two ODEs 
$$
\begin{rcases}T''(t)=\mu c^2 T(t)\\ X''(x)=\mu X(x)\end{rcases} \text{ Ques: What kind of solution will we have for X if }\begin{cases}\mu>0\\\mu<0\end{cases}
$$
Lets take the two cases:
For $\mu>0$, assume $\mu=k^2$
$$
\begin{rcases}T''(t)=(kc)^2 T(t)\\[0.5em] X''(t)=k^2 X(x)\end{rcases}\,\,\,\,\, \begin{array}{c}T(t)=Ae^{kct}+Be^{-kct}\\ X(x)=Ce^{kx}+De^{-kx}\end{array}
$$
For $\mu <0$
$$
\begin{rcases}T''(t)=-(kc)^2 T(t)\\[0.5em] X''(t)=-k^2 X(x)\end{rcases}\,\,\,\, \begin{array}{c}T(t)=A\cos k_c t+B\sin k_ct\\ X(x)=C\cos(kx)+D\sin(kx)\end{array}
$$

For wave and heat equations $\mu <0$.
But for Laplace, it depends.

The boundary and initial conditions may not be separable. (not a big problem)

Homogenous boundary conditions and initial conditions can be separated.
	Example: $0=u(0,t)=X(0)T(t)\Rightarrow \boxed{X(0)=0}$

Similarly, 
$$
0=u(L,t)=X(L)T(t)\Rightarrow \boxed{X(L)=0}
$$
Homogenous LC. $u_t(x,0)=0$
$$
u_t(x,0)=X(x)T'(0)\,\,\,\,\,\,\, \boxed{T'(0)=0}
$$
___
Is it $\mu >0$ or $\mu<0$?

For $\mu>0$: $X(x)=Ce^{kx}+De^{-kx}$
	The exponential functions cant reach zero, so either C or D would be zero. But we know that X can never be zero, so this is a contradiction, and thus $\mu$ can never be greater than $0$.

We have
$$
\begin{array}{c}T(t)=A\cos(kct)+B\sin(kct)\\[0.5em] X(x)=C\cos(kx)+D\sin(kx)\end{array}
$$
$$
0=X(0)=C\,\,\,\,\,\,\, \Rightarrow X(x)=D\sin(kx)
$$
and
$$
0=X(L)=D\sin(kL)\,\,\,\,\Rightarrow kL=n\pi,\,\, n\in Z
$$
Hence
$$
\boxed{k=\frac{n\pi}{L}}\,\,\,\,\text{ and }\,\,\, \boxed{X_n(x)=D_n\sin\left(\frac{x\pi x}L\right)}
$$

The Homogenous Initial condition
$$
T'(0)=0
$$
$$
T(t)=A\cos(kct)+B\sin(kct)
$$
$$
T'(t)=-kcA\sin(kct)+kcB\cos(kct)
$$
$$
T'(0)=kcB=0\,\,\,\,\,\, \Rightarrow B=0
$$
We know that $k=\frac{n\pi}{L},\,\,\,\, n\in Z$ 
Hence,
$$
T_n(t)=A_n\cos\left(\frac{n\pi ct}{L}\right)
$$
___
Putting it all together
$$
\boxed{u(x,t)=\sum_{n=1}^\infty b_n\sin\left(\frac{n\pi x}L\right)\cos\left(\frac{n\pi ct}L\right)}
$$
where
$$
b_n=A_nD_n
$$

The initial condition $u(x,0)=f(x)$
$$
u(x,0)=\sum_{n=1}^\infty b_n\sin\left(\frac{n\pi x}L\right)=f(x)
$$
$$
\boxed{b_n=\frac{2}L\int_0^L f(x)\sin\left(\frac{n\pi x}{L}\right)dx}
$$
____
### Example 5.1
Lets choose $L=4$ and
$$
f(x)=\begin{cases}x&0\le x\le 2\\ 4-x&2<x\le 4\end{cases}
$$
This is a triangle shaped function, which potentially is periodic.
$$
b_n=\frac{2}4\int_0^4 f(x)\sin\left(\frac{n\pi x}4\right)dx
$$
$$
=\frac{1}2 \int_0^2 x\sin\left(\frac{n\pi x}4\right)dx+\int_2^4 (4-x)\sin\left(\frac{n\pi x}4\right) dx
$$
$$
b_n=\frac{16}{(n\pi)^2}\sin\left(\frac{n\pi}2\right)\,\,\,\,\,\,\,\,\, n=1,2,3,4,5
$$
$$
u(x,t)=\sum_{n=1}^\infty \frac{16}{(n\pi)^2}\sin\left(\frac{n\pi}2\right)\sin\left(\frac{n\pi x}4\right)\cos\left(\frac{n\pi ct}4\right)
$$

This is how the function $u(x,t)$ looks like plotted in 3D

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240130155102.png]]

