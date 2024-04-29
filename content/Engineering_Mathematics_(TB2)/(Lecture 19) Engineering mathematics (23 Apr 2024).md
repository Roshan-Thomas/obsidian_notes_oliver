---
title: Lecture 19
date: 23 Apr 2024
---
# Revision
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240429223421.png]]

Question gives us that the general solution of the PDE
$$
u(x,t)=\sum_{n=1}^\infty A_n\cos\left(\frac{n\pi x}L\right)\sin\left(\frac{n\pi ct}L\right)
$$
is a solution of the PDE for how many every boundary or initial conditions are there.

We just have to find $A_n$ by solving the non-homogenous initial conditions
$$
\frac{\partial u}{\partial t}=V(x)\,\,\,\,\,\,\,\,\text{ at }t=0
$$
$$
\begin{split}\left.\frac{\partial u}{\partial t}\right|_{t=0}&=\sum_{n=1}^\infty \left.A_n\cos\left(\frac{n\pi x}L\right)\cos\left(\frac{n\pi ct}L\right)\frac{n\pi c}{L}\right|_{t=0}\\ V(x)&=\sum_{n=1}^\infty \underbrace{A_n\frac{n\pi c}L}_{a_n}\cos\left(\frac{n\pi x}L\right)   \end{split}
$$
From question,
$$
a_n=\frac{8}{n^2\pi^2}\left(\cos\left(\frac{n\pi}4\right)+\dots\right)=A_n\cdot \frac{n\pi c}L
$$
$$
A_n=\frac{L}{n\pi c}\frac{8}{n^2\pi^2}\left(\cos\left(\frac{n\pi}4\right)+\dots\right)
$$
___
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240429224358.png]]

Solution of wave equation in an infinite domain, and that means the d'Alembert solution.
$$
u(x,t)=f(x-ct)+g(x+ct)
$$
We have to find what the two functions $f$ and $g$ are, by applying the initial conditions
$$
u=e^{-x2/4}\,\,\,\,\,\,\text{ at }t=0
$$
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240429224717.png]]

$$
\frac{\partial u}{\partial t}=0\,\,\,\,\,\,\text{ at }t=0
$$
Substituting d'Alembert solution into the initial conditions,
$$
u(x,0)=\boxed{f(x)+g(x)=e^{-x^2/4}}\,\,\,\,\text{ for all x}
$$
$$
\begin{split}\frac{\partial u}{\partial t}(x,0)&=\left.\frac{\partial}{\partial t}\left[f(x-ct)+g(x+ct)\right]\right|_{t=0}\\ &=-\left.cf'(x-ct)+cg'(x+ct)\right|_{t=0}\\ &=\boxed{-cf'(x)+cg'(x)=0}\,\,\,\text{for all x}\end{split}
$$
We need to integrate with respect to x
$$
\boxed{-f(x)+g(x)=A}
$$
Adding the resulting equations,
$$
\begin{array}{c}2g(x)=e^{-x^2/4}+A\\ g(x)=\frac 1 2 e^{-x^2/4}+\frac{A}2\end{array}
$$
Subtracting the resulting equations
$$
\begin{array}{c}2f(x)=e^{-x^2/4}-A\\ f(x)=\frac 1 2 e^{-x^2/4}-\frac A 2\end{array}
$$
So,
$$
\begin{split}u(x,t)&=f(x-ct)+g(x+ct)\\ &=\frac{1}2 e^{-(x-ct)^2/4}-\frac A 2+\frac 1 2 e^{-(x+ct)^2/4}+\frac A 2\\ &=\frac{1}2 e^{-(x-ct)^2/4}+\frac 1 2 e^{-(x+ct)^2/4}\end{split}
$$
Sketching the resulting curves,

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240429225710.png]]


