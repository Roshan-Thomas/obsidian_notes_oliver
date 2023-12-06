---
title: Lecture 9
date: 06 Dec 2023
---
# Recap
![[Principles_of_Physical_Modelling/images/Pasted-image-20231206091231.png|400]]
$$
F(X,t)=F(\chi^{-1}(x,t),t)=f(x,t)
$$
where $x=\chi(X,t)$ and $X=\chi^{-1}(x,t)$
$$
f(x,t)=f(\chi(X,t),t)\cdot F(X,t)
$$
$$
\frac{dF}{dt}=\left.\frac{\partial F}{\partial t}\right|_x=\left.\frac{\partial}{\partial t}f(\chi(X,t),t)\right|_x=\left.\frac{\partial f}{\partial t}\right|_x+\left.\frac{\partial X}{\partial t}\right|_x\frac{\partial f}{\partial x}
$$
In one dimension:
$$
g(x),\,\,\,\, x=h(u),\,\,\,\,\, g(h(u))
$$
$$
\frac{dg}{dx}=\frac{dg}{du}\frac{du}{dx}\tag{Chain rule}
$$
___
## Example
$$
F=\sin(X),\,\,\,\,\,\,\,\,\,\, x=X+t
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231206092548.png|400]]
$$
\sin(x,t)=f(x,t)
$$
$$
F(\chi^{-1}(X,t))=\sin(x-t)=f(x,t)
$$
$$
f(\chi(X,t),t)=\sin(X)=F(X)
$$
So,
$$
\left.\frac{\partial F}{\partial t}\right|_x=0
$$
$$
\left.\frac{\partial f}{\partial t}\right|_x=-\cos(x-t)
$$
We can see that $\frac{\partial F}{\partial t}\ne\frac{\partial f}{\partial t}$

![[Principles_of_Physical_Modelling/images/Pasted-image-20231206093059.png|400]]

The red line symbolises the Eulerian coordinate system.

To make $\frac{\partial F}{\partial t}=\frac{\partial f}{\partial t}$,
$$
\left.\frac{\partial f}{\partial t}\right|_x+\cos(x-t)=0=\left.\frac{\partial F}{\partial t}\right|_x
$$
where, $\frac{\partial \chi}{\partial t}=1$, and $\frac{\partial f}{\partial t}=\cos(x-t)$
___
# Introduction to fluid mechanics
The Navier-Stokes equations as seen on the slides
where
$$
\vec V=(u,v,w)
$$
$$
\nu=\frac{\mu}{\rho}
$$
Consider the simpler case,
$$
\vec V=(u(x,y,z,t),0,0)
$$
Notation: $u_x=\frac{\partial u}{\partial x}$
The system of equation boils down to 
$$
u_x=0\tag{1}
$$
$$
u_t=-\frac{1}{\rho}p_x+v(u_{yy}+u_{zz})\tag{2}
$$
$$
0=-\frac{1}{\rho}p_y\tag{3}
$$
$$
0=-\frac{1}{\rho}p_z\tag{4}
$$
From (1)
$$
u_x=0\,\,\,\,\rightsquigarrow u(y,z,t)=u
$$
From (2)
$$
u_t=-\frac{1}{\rho}p_x+v(u_{yy}+u_{zz})
$$
From (3) and (4), it tells us that 
$$
\rightsquigarrow p=p(x,t)
$$
So we end up with,
$$
\boxed{\frac{\partial u}{\partial t}=v(u_{yy}+u_{zz})=-\frac{1}{\rho}p_x}
$$
By making this reduction, you can use this to solve problems now.

At the moment, we have $u(y,z,t)$ and $p(x,t)$. The strange thing is that on the left hand side we the function is in terms of $y,z,t$ but the right hand side is a function of $x,t$. 
Then the only we the terms can be equal,
$$
\frac{\partial u}{\partial t}-v\left(\frac{\partial^2 u}{\partial y^2}+\frac{\partial^2}{\partial z^2}\right)=-\frac{1}{\rho}\frac{\partial p}{\partial x}=G(t)
$$
$$
-\frac{1}{\rho}\frac{\partial p}{\partial x}=G(t)
$$
$$
\boxed{\frac{\partial u}{\partial t}-v\left(\frac{\partial^2u}{\partial y^2}+\frac{\partial^2u}{\partial z^2}\right)=G(t)}\tag{Need to specify G(t)}
$$
## Example
Take two plates one at $z=0$ and the other one at $z=h$, and you move the plate at $h$ along one axis, and you have viscous fluid in between the plates.
![[Principles_of_Physical_Modelling/images/Pasted-image-20231206102954.png]]

At $t=0$,   $\vec v=0=(0,0,0)$,     $u=u(y,z,0)=0$ (initial condition)
Assume $u=u(z,t)$
$$
\frac{\partial u}{\partial t}=v\frac{\partial^2u}{\partial z^2}-\frac{1}{\rho}\frac{\partial p}{\partial x},\,\,\,\,\,\,\,\,-\frac{1}{\rho}\frac{\partial p}{\partial x}=G(t)
$$
The relevant boundary conditions of a viscous fluid is 'no-slip condition', where $\text{fluid velocity}=\text{boundary velocity}$, basically the fluid does not move with the plane at $h$.

$$
\vec V=(u,0,0)=\vec V_B\,\,\,\,\,\,\,\,\rightsquigarrow u(0,t)=0,\,\,\, u(H,t)=U
$$
Assume $G(t)=0$ and the flow is steady (this means time-independent)
$$
\frac{\partial^2 u}{\partial z^2}=0,\,\,\,\,\,\,\,\,\,\,\, u(0,t)
=0,\,\,u(H,t)=U
$$
$$
\frac{d^2 u}{dz^2}=0\,\rightsquigarrow u=Az+B
$$
When A=0, $u(0,t)=0\implies B=0$
$$
\begin{align*}u(H,t)=u&\rightsquigarrow U=AH\\&\rightsquigarrow A=\frac{U}{H}\end{align*}
$$
$$
\boxed{u=\frac{Uz}{H}}
$$
This case is called "Plane-parallel shear flow"
## Example
In this case, instead of shearing the top plate, we keep it fixed (velocities = 0)
![[Principles_of_Physical_Modelling/images/Pasted-image-20231206104516.png|400]]
Assume $G(t)\ne 0$ i.e. "pressure-driven"
$$
G(t)=G_0
$$
$$
\nu\frac{\partial^2 u}{\partial z^2}-G(t)=0
$$
$$
u(0,t)=u(H,t)=0
$$
This means that
$$
\begin{rcases}\nu\frac{\partial u}{\partial z}=G_0 z+A\\\nu u=\frac{1}{2}G_0z^2+Az+B\end{rcases}\begin{align*}u(0,t)=0\rightsquigarrow B=0\\ u(H,t)=0\end{align*}
$$
$$
0=\frac{1}{2}G_0H^2+AH
$$
$$
A=-\frac 1 2 G_0 H
$$

So,
$$
u=\frac{1}{2}G_0z^2-\frac{1}{2}G_0Hz
$$
$$
\boxed{u=\frac{1}{2}G_0z(z-H)}
$$
So the velocity follows this parabolic profile.

![[Principles_of_Physical_Modelling/images/Pasted-image-20231206105011.png|400]]

This type of flow is called 'Poiseuille flow'






