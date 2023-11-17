---
title: Lecture 14
date: 17 Nov 2023
---
**Worked Example 7.2**

Continued from last Lecture [[(Lecture 13) Engineering Mathematics - 2 (14 Nov 2023)]]

The First part of the integral is:
$$
\int\vec F\cdot d\vec r=\int_{t=0}^{2\pi}\vec F(\vec r_c(t))\cdot \left(\frac{d\vec r_c}{dt}\right)\, dt
$$
$$
=\int_{t=0}^{2\pi} (\sin t,0,\cos t)\cdot(-\sin t,\cos t, 0)dt
$$
$$
=\int_{t=0}^{2\pi}-\sin^2 t\, dt
$$
$$
=\int_{t=0}^{2\pi}-\left(\frac{1-\cos 2t}{2}\right)\, dt=-\pi
$$
The second part of the integral
$$
\int\int(\vec\nabla\times E)\cdot d\vec A
$$
$$
\nabla\times F=(\partial_x,\partial_y,\partial_z)\times(y,z,x)=(-1,-1,-1)
$$
$$
d\vec A=\left(\frac{\partial \vec r_s}{\partial \rho}\times\frac{\partial \vec r_s}{\partial \theta}\right)\, d\rho\, d\theta
$$
$$
=(\cos\theta,\sin\theta,-2\rho)\times(-\rho\sin\theta, \rho\cos\theta, 0)\, d\rho\, d\theta
$$
$$
=\underbrace{(2\rho^2\cos\theta,-2\rho^2\sin\theta,\rho)}_{\vec n(\rho,\theta)}\, d\rho\,d\theta
$$
$$
\int\int_S (-1,-1,-1)\cdot (2\rho^2\cos\theta,2\rho^2\sin\theta,\rho)\, d\rho\,d\theta
$$
$$
\int\int(-2\rho^2\cos\theta+2\rho^2\sin\theta-\rho)\, d\rho\,d\theta
$$
$$
\int_{\theta=0}^{2\pi}\left(-2\frac{\rho^3}3 \cos\theta+2\frac{\rho^3}3 \sin\theta-\frac{\rho^2}{2}\right\vert_{0}^1\, d\theta
$$
$$
\int_{\theta=0}^{2\pi}\left(-\frac{2}3 \cos\theta+\frac{2}3 \sin\theta-\frac{1}2\right)\, d\theta=-\pi
$$
So,
$$
\int\vec F\cdot d\vec r=-\pi
$$
$$
\int\int(\nabla\times F)\cdot d\vec A=-\pi
$$
___
**Worked Example 7.3**
$$
\vec D=\frac{q\hat{\vec r}}{4\pi|\vec r|^2}=\frac{q\vec r}{4\pi |\vec r|^3}
$$
- When we have a charge $q$, the electric field would radiate away from the charge.

![[Engineering-Mathematics---2/images/Pasted-image-20231117152941.png|200]]
$$
\int\int\vec D\cdot d\vec A=q
$$
$$
d\vec A=\vec r^2 a^2\,\sin\theta\, d\theta\, d\phi
$$
$$
\iint_{SA}\vec D\cdot d\vec A=\iint_{SA}\left(\frac{q\hat{\vec r}}{q\pi|\vec r|^2}\right)\cdot \hat{\vec r}a^2\sin\theta\, d\theta\, d\phi
$$
$$
=\frac{q}{4\pi}\underbrace{\iint \sin\theta\, d\theta\,d\theta}_{4\pi}=q
$$
Instead of a spherical cover surrounding the charge, imagine we have an uneven surface surrounding $q$.
![[Engineering-Mathematics---2/images/Pasted-image-20231117153449.png|300]]

Using the divergence theorem
$$
\iint_S\vec D\cdot d\vec A=\iiint_V(\vec\nabla\cdot\vec D)dV
$$
$$
\iint_S\vec D\cdot d\vec A=q+\iiint_{V-V_a}\vec \nabla\cdot \vec D\, dV
$$
$$
\vec\nabla \cdot\vec D=0;\,\,\,\,\,\,\,\vec r\ne0
$$
So the total flux at any arbitrary surface is the charge q and doesn't matter the shape or size that encloses the charge.
$$
\iint_S\vec D\cdot d\vec A=q=\iiint_V\vec \nabla\cdot \vec D\, dV
$$
