---
title: Lecture 9
date: 24 Oct 2023
---
**Worked example 4.2**

Part (b)
We have a helix as see in the image

![[Engineering-Mathematics---2/images/Pasted-image-20231024150807.png|200]]

Parameterizing the curve
$$
\vec r(t)=(a\cos t,a\sin t, bt)
$$
$$
s=\int\vert d\vec r\vert=\displaystyle\int_{t=0}^{2\pi} \left\vert\frac{d\vec r}{dt}\right\vert dt
$$
$$
\frac{d\vec r}{dt}=(-a\sin t,a\cos t, b)
$$
$$
\left\vert \frac{d\vec r}{dt}\right\vert=\sqrt{a^2\sin^2 t+a^2\cos^2 t+b^2}
$$
$$
=\sqrt{a^2+b^2}
$$
This tells us that the size of the curve does not change over time
$$
s=\displaystyle\int_{t=0}^{2\pi}\sqrt{a^2+b^2}dt
$$
$$
=2\pi\sqrt{a^2+b^2}
$$
___

**Worked Example 4.5**

Find the work done in moving from $(0,0,0)$ to $(1,1,1)$ in the force field $F$ given by 
$$
\vec F=(2xy+z^3)\vec i+x^2\vec j+2xz^2\vec k
$$
**Solution**

1. $\vec r(t)=(t,t,t)$ 

2. Endpoints: $t=0, t=1$

3. Work Integral
$$
\int_{A\,(0,0,0)}^{B\,(1,1,1)}\vec F(\vec r)\cdot d\vec r
$$

$$
\int_{t=0}^{1} \left(\vec F(\vec r(t))\cdot \frac{d\vec r}{dt}\right)dt
$$
$$
\begin{cases}\frac{d\vec r}{dt}=(1,1,1)\\[0.5em] \vec F(\vec r(t))=(2t^2+t^3, t^2, 3t^2)\end{cases}
$$
$$
\int_{t=0}^1 (3t^2+4t^3)dt=2
$$

# Conservative Vector Fields & Path indendence

If the vector field $F$ is conservative then the work integral is **independent** from the path.

**Worked Example 4.6**
$$
\vec F=\left(2xy+z^3,x^2,3xz^2\right)
$$
Homework: Check the curl of Force is zero. $\vec\nabla\times \vec F=0$

$$
\vec F=\vec\nabla\phi=\begin{pmatrix}\frac{\partial\phi}{\partial x}\\ \frac{\partial\phi}{\partial y}\\ \frac{\partial\phi}{\partial z}\end{pmatrix}=\begin{pmatrix}2xy+z^3\\ x^2\\ 3xz^2\end{pmatrix}
$$
Lets look at the individual equations
The first equation:
$$
\frac{\partial\phi}{\partial x}=2xy+z^3\,\,\,\therefore\phi=\int dx(2xy+z^3)
$$
$$
\phi=x^2y+xz^3+C(y,z)
$$
The second equation:
$$
\frac{\partial\phi}{\partial y}=x^2\,\,\,\,\,\therefore x^2+\frac{\partial C}{\partial y}=x^2
$$
$$
\frac{\partial C}{\partial y}=0
$$
So,
$$
C(y,z)=C(z)
$$
The third equation:
$$
\frac{\partial\phi}{\partial z}=3xz^2
$$
$$
3xz^2+\frac{\partial C}{\partial z}=2xz^2
$$
$$
\therefore \frac{\partial C}{\partial z}=0
$$
So,
$$
\boxed{\phi=x^2y+xz^3+d}
$$
As the field is conservative, the work done
$$
W=\phi(1,1,1)-\phi(0,0,0)
$$
$$
=(1+1+d)-(0+0+d)
$$
$$
=2
$$
You get the same result as *Worked example 4.2*. 

### Central Fields
If you have a central field that radiates from a single point (origin), then the magnitude of the force field 
$$
\vec F=\frac{df(r)}{dr}\hat r
$$
for some scalar function $f$
