---
title: Lecture 2
date: 29 Sept 2023
---

**Example 1.2:** Projectile falling under gravity 
$$
\vec a=\frac{d^2r}{dt^{2}}=-g\vec k
$$
The initial conditions are:
- $\vec r(t=0)=0$
- $\frac{d\vec r}{dt}(t=0)=v_{0} \vec i$ 
To solve a second order differential equation
Integrate: 
$$
\int^{t} \frac{d^{2}\vec r}{dt^{2}}=\int^{t}-g\vec k\, dt
$$
$$
\frac{dr}{dt}=-g\vec k\, t+c
$$
at $t=0$ 
$$
v_{0}\vec i=0+c
$$
So, 
$$
\frac{dr}{dt}=-g\vec k\, t+v_{0}\vec i
$$
Integrate again 
$$
\int\frac{dr}{dt}dt=\int^{t}\left(-g\vec k t+v_{0}\vec i\right)dt
$$
$$
\vec r(t)=-g\vec k \frac {t^{2}} {2}+v_{0}\vec it+\cancel{d}^{\, 0}
$$
The constant $d$ is cancelled to 0 by $\vec r(t=0)=0$

# Scalar Fields
A common way to represent scalar fields is by level curves, where each curve is constant pressure. 
![[Engineering-Mathematics---2/images/Pasted image 20230929152435.png | 200]]

A **maxima/minima** of the curves can be found by a concentration of curves at a particular point. 

A **saddle point** can be found by a lack of concentric curves at a particular point in the scalar field. They look like hyperbolic curves at a saddle point.

Example: $x^2+y^2+z^2$

# Vector Fields
Vector fields are field maps where each point is given a direction and a length (vectors).
![[Engineering-Mathematics---2/images/Pasted image 20230929153315.png | 250]]

# Cartesian Coordinates
The cartesian coordinates are $x,y,z$. Their components are $\vec i, \vec j, \vec k$ respectively. 
To describe a point in cartesian coordinates we write 
$$
r(x,y,z)=x\vec i+y\vec j+z\vec k
$$ 

![[Engineering-Mathematics---2/images/Pasted image 20230929154252.png]]
# Polar Coordinates 

![[Engineering-Mathematics---2/images/Pasted image 20230929154512.png]]

$$
\vec r =|\vec r|\hat r
$$



