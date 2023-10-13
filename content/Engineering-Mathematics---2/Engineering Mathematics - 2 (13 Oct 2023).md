---
title: Lecture 6
date: 13 Oct 2023
---
### Fluid Mechanics: Vortex
Axial symmetric vector field 
$$
\vec v=\frac{\hat\theta}{|\vec r|}
$$
where $\vec r=(x,y)$, $\vec\theta=(-y,x)$ 
$$
\vec\theta\cdot\vec r=0
$$
$$
\vec{\hat\theta}=\frac{\vec \theta}{|\vec\theta|}=\frac{(-y,x)}{|\vec r|}
$$
$$
|\vec r|=\sqrt{x^2+y^2}=|\vec\theta|
$$
In Cartesian coordinates
$$
\vec v^{(x,y)}=\left(\frac{-y}{x^2+y^2},\frac{x}{x^2+y^2}\right)
$$
Calculating the **divergence**
$$
\begin{align}\vec\nabla\cdot\vec v=\frac{\partial}{\partial x}\left(\frac{-y}{x^2+y^2}\right)+\frac{\partial}{\partial y}\left(\frac{x}{x^2+y^2}\right)\end{align}
$$
$$
\frac{\partial}{\partial x}\left(\frac{-y}{x^2+y^2}\right)=\frac{\partial}{\partial x}\Bigg\{-y(x^2+y^2)^{-1}\Bigg\}
$$
$$
=-y\times-1(x^2+y^2)^{-2}\times 2x
$$
$$
\frac{\partial}{\partial y}\left(\frac{x}{x^2+y^2}\right)=-2yx(x^2+y^2)^{-2}
$$
Adding the above two terms to calculate the divergence
$$
\therefore\vec\nabla\cdot\vec v=0,\,\,\,\,\, \forall(x,y)\ne0
$$
Calculating the **curl**
$$
\vec\nabla\times\vec v=\begin{vmatrix}\vec i&\vec j&\vec k\\ \frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\ \frac{-y}{x^2+y^2} & \frac{x}{x^2+y^2}&0 \end{vmatrix}
$$
$$
=\vec k\left(\frac{\partial}{\partial x}\frac{x}{x^2+y^2}+\frac{\partial}{\partial y}\frac{y}{x^2+y^2}\right)
$$
$$
\frac{\partial}{\partial x}\frac{x}{x^2+y^2}=\frac{\partial}{\partial x}x(x^2+y^2)^{-1}
$$
$$
=(x^2+y^2)^{-1}-2x^2(x^2+y^2)^{-2}
$$
$$
\frac{\partial}{\partial y}\frac{y}{x^2+y^2}=(x^2+y^2)^{-1}-2y^2(x^2+y^2)^{-2}
$$
Equating the above terms to calculate the curl
$$
\therefore\vec\nabla\times\vec v=\frac{2}{x^2+y^2}-\frac{2(x^2+y^2)}{(x^2+y^2)^2}=0,\,\,\,\,\, \forall(x,y)\ne 0
$$
## Irrotational flow, conservative forces
**Irrotational**: If the $\text{curl }\vec v=0$ then the flow of the velocity field is called irrotational

**Conservative**: A force field that satisfies $\text{curl }F=0$ is called conservative

Important identity
$$
\boxed{\vec\nabla\times\vec v=0\Leftrightarrow \vec v=\vec\nabla\phi}
$$
where $\phi$ is called the **scalar potential** f a conservative vector field.

**Worked example 3.3**

Find scalar functions $\phi$ whose gradients $\vec\nabla\phi$ are:
1. $(2xy+z^3)\vec i+x^2\vec j+2xz^2\vec k$

**Solution**
$$
\vec v=(2xy+z^3, x^2, 3xz^2)
$$
$$
\vec v=\vec\nabla\phi=\left(\frac{\partial\phi}{\partial x}, \frac{\partial\phi}{\partial y},\frac{\partial \phi}{\partial z}\right)
$$
x-component
$$
\frac{\partial\phi}{\partial x}=2xy+z^3
$$
$$
\Rightarrow \phi=\int dx(2xy+z^3)
$$
$$
\therefore \phi=x^2y+z^3x+f(y,z)
$$
y-component
$$
\frac{\partial\phi}{\partial y}=x^2
$$
$$
\Rightarrow \phi=\int dy(x^2)
$$
$$
\therefore \phi=x^2y+g(x,z)
$$
z-component
$$
\frac{\partial \phi}{\partial z}=3xz^2
$$
$$
\Rightarrow\phi=\int dz(3xz^2)
$$
$$
\therefore \phi=xz^3+h(x,y)
$$
Therefore, adding all the components together
$$
\phi=x^2y+z^3x+\text{constant}
$$

*Checking*
$$
\vec\nabla\phi=\begin{pmatrix}2xy+z^3\\ x^2\\ 2z^2x\end{pmatrix}
$$


