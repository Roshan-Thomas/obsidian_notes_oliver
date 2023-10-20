---
title: Lecture 8
date: 20 Oct 2023
---
Note: Drop-in's in Queen's Building 1.68 & 1.69
# Integration along curves
## Path integrals of scalar and vector fields 

**Worked Example 4.1**

Calculate the work done by moving along a straight line from A at $(2,1,1)$ to B at $(3,2,2)$ in a force field
$$
\vec F=\frac{\vec r}{|\vec r^2|}=\frac{x\vec i+y\vec j+z\vec k}{x^2+y^2+z^2}
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231020153320.png|250]]
$$
W=\int_A^B\vec F(r)\cdot dr
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231020153700.png|250]]
$$
W=\displaystyle\int_{t=t_0}^{t_1} F(\vec r(t))\cdot\left(\frac{dr}{dt}\right)dt
$$
Find $\vec r(t)$, and then find $F(\vec r(t))$ and then find the derivative $F\left(\frac{dr}{dt}\right)$ and then integrate.
$$
\vec r(t)=(2,1,1)+(1,1,1)t
$$
$$
\boxed{\vec r(t)=(2+t,1+t, 1+t)}=\left(x(t),y(t),z(t)\right)
$$
$$
\frac{dr}{dt}=(1,1,1)
$$
The force field 
$$
\vec F(\vec r)=\vec F(\underbrace{x}_{x(t)}\,,\underbrace{y}_{y(t)}\,,\underbrace{z}_{z(t)})=\frac{(x,y,z)}{x^2+y^2+z^2}
$$
$$
\vec F(\vec r(t))=\frac{(2+t, 1+t, 1+t)}{(2+t)^2+(1+t)^2+(1+t)^2}
$$
The integral
$$
\int\left(\vec F(r(t))\cdot\frac{dr}{dt}\right)dt
$$
$$
\int_{t=0}^1\frac{2+t+1+t+1+t}{\left(3t^2+8t+6\right)}\cdot(1,1,1)dt
$$
Calculating the definite integral
$$
\implies\ln\sqrt{\frac{17}{6}}
$$

