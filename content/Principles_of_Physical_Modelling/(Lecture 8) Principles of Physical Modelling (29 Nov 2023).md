---
title: Lecture 8
date: 29 Nov 2023
---
# Recap
One-dimension

![[Principles_of_Physical_Modelling/images/Pasted-image-20231129091233.png|500]]
- Here $x\in\Re=\{a_0,b_0\}$

At $t=0$, $a_0\le X\le b_0$
When you apply forces to this object, the object stretches out, and each point on the initial bar is present on the new bar (line) as well. This point $x$ is known as the Eulerian coordinate.
![[Principles_of_Physical_Modelling/images/Pasted-image-20231129091703.png|500]]
Note: Eulerian coordinate is sometimes called spatial coordinates as it is fixed in space (not fixed in material).
$$
\boxed{x=\chi(X,t)}
$$
$\chi$ tells us the deformation of the object through some forces over a period of time.
$$
\boxed{X=\chi^{-1}(x,t)}
$$
$$
J=\frac{dx}{dX}\ne0
$$
A pictorial representation of these two coordinate systems
![[Principles_of_Physical_Modelling/images/Pasted-image-20231129092849.png|400]]

![[Principles_of_Physical_Modelling/images/Pasted-image-20231129092940.png|400]]

Each line on the first graph is directly mapped onto the line in the second graph i.e. bijective function.

**Displacement**:
$$
U(X,t)=x-X
$$
$$
=\chi(X,t)-X\tag{Lagrangian coordinates}
$$
The function $U$ measures the difference between the distance of point $x$ and $X$ (starting point).

**Velocity**:
$$
\frac{dU}{dt}=\left.\frac{dU}{dt}\right|_x=V(X,t)
$$
$$
=\frac{d\chi}{dt}=V(X,t)
$$
$$
u(x,t),\,\,\, v(x,t)\tag{Eulerian coordinates}
$$
To convert from Eulerian coordinates to Lagrangian coordinates
$$
u(\chi(X,t), t),\,\,\,\, v(\chi(X,t),t)
$$
$$
=U(X,t),\,\,\,\, =V(X,t)
$$
So displacement
$$
u(x,t)=U(\chi^{-1}(x_1(\_),t))
$$
So velocity
$$
v(x,t)=V(\chi^{-1}(x_1(\_), t))
$$
Note: $\frac{dU}{dt}=V(x,t)$ it is not true $\frac{du}{dt}=v(x,t)$
$$
\frac{dU}{dt}=\left.\frac{\partial u}{\partial t}\right|_x=\frac{\partial u}{\partial t}+\frac{\partial \chi}{\partial t}\frac{\partial u}{\partial X}\tag{Chain rule}
$$
$$
\frac{dU}{dt}=\left.\frac{\partial u}{\partial t}\right|_x+v(x,t)\frac{\partial u}{\partial x}\tag{Material Derivative}
$$
More generally,
$$
\boxed{\frac{df}{dt}=\frac{\partial f}{\partial t}+v(x,t)\frac{\partial f}{\partial x}}
$$
____
## Example
Consider a deformation defined by
$$
x=\chi(X,t)=Xe^t
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231129094937.png]]
The above image shows how each point behaves in the Lagrangian coordinate space and the Eulerian coordinate space.

Consider the material point currently at $x=2$ at time $t=5$. Where was this point at $t=0$?

We are trying to work out $x=\chi(X,0)=X$
$$
x=2=x(X,t=5)=Xe^5\rightsquigarrow X=2e^{-5}
$$
$$
\boxed{x=2e^{-5}e^t=2e^{t-5}}
$$
$$
x=x(X,t)=Xe^t
$$
For displacement
1. $U(X,t)=X(e^t-1)$
2. $u(x,t)=xe^{-t}(e^t-1)=x(1-e^{-t})$
$$
u(\chi(x,t),t)=U(X,t)
$$
$$
u(x,t)=U(\chi^{-1}(X,t),t)
$$
For velocity
1. $V(X,t)=Xe^t\rightsquigarrow x=Xe^t$
2. $v(x,t)=xe^{-t}=x$
	Note: $\frac{\partial u}{\partial t}\ne v(x,t)$, and $xe^{-t}\ne x$

$$
\left.\frac{\partial u}{\partial t}\right|_x+v(x,t)\frac{\partial u}{\partial x}=xe^{-t}+x(1-e^{-t})
$$
$$
=x=v(x,t)
$$
___
In this course, we try to look at problems that can be simplified down into 1 dimensional

$$
\frac{\partial\rho}{\partial t}+\nabla\cdot(\rho\vec v)=0
$$
$$
\rho\frac{d\vec v}{dt}=\nabla\cdot\sigma
$$
where
$$
\sigma=\begin{pmatrix}\sigma_{11}&\sigma_{12}&\sigma_{13}\\\sigma_{21}&\sigma_{22}&\sigma_{23}\\\sigma_{31}&\sigma_{32}&\sigma_{33}\end{pmatrix}
$$
We know from Engineering Mathematics - 2
$$
\nabla\cdot\vec F=\frac{\partial F_x}{\partial x}+\frac{\partial F_y}{\partial y}+\frac{\partial F_z}{\partial z}
$$
$$
\vec F=(F_x,F_y,F_z)
$$
$$
\nabla=\left(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial }{\partial z}\right)
$$
So,
$$
\nabla\cdot\sigma=\begin{pmatrix}\cfrac{\partial\sigma_{11}}{\partial x}+\cfrac{\partial \sigma_{12}}{\partial y}+\cfrac{\partial\sigma_{13}}{\partial z}\\ \cfrac{\partial\sigma_{21}}{\partial x}+\cfrac{\partial \sigma_{22}}{\partial y}+\cfrac{\partial\sigma_{23}}{\partial z}\\ \cfrac{\partial\sigma_{31}}{\partial x}+\cfrac{\partial\sigma_{32}}{\partial y}+\cfrac{\partial\sigma_{33}}{\partial z}\end{pmatrix}
$$
We have 13 unknowns, but only 4 equations

Write $\sigma=\sigma(\rho,\vec u,\vec v,\nabla u,\dots)$

Consider two cases: inviscid fluid (no viscosity) and viscous fluid

#### Inviscid fluid
$$
\sigma=-pI=\begin{pmatrix}-p&0&0\\0&-p&0\\0&0&-p\end{pmatrix},\,\,\,\,\,\,\,p=p(x,y,z,t)
$$
So the only force that acts on this fluid is the pressure
![[Principles_of_Physical_Modelling/images/Pasted-image-20231129104658.png|400]]
$$
\frac{\partial p}{\partial t}+\nabla\cdot(p\vec v)=0
$$
$$
p\frac{d\vec v}{dt}=\nabla\cdot\sigma=\begin{pmatrix}-\cfrac{dp}{dx}\\-\cfrac{dp}{dy}\\-\cfrac{dp}{dz}\end{pmatrix}=-\nabla p
$$
We started with so many unknowns, but by defining the constituent law (defining $\sigma$) we reduced it down to 5 unknowns but with 4 equations.

$$
p=p(\rho,\vec u)\rightsquigarrow\text{For a "barotropic" gas, }p=p(\rho)
$$
So,
$$
p\frac{d\vec v}{dt}=-\frac{dp}{d\rho}\nabla p
$$
#### Viscous Case
$$
\sigma=-pI+\mu(\nabla \vec v+\nabla\vec v^T)
$$


















