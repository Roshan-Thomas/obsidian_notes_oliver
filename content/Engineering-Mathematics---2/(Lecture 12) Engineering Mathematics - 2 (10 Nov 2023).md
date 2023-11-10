---
title: Lecture 12
date: 10 Nov 2023
---
**Worked Example 5.8**

$$
z=(x^2+y^2)
$$
$$
(x^2+y^2)=r^2,\,\,\,\,\,\,\text{here, z is unconstrained, so its a cylinder and not a sphere}
$$
$$
z=a^2
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231110150936.png|200]]
The Volume
$$
V=\int_{z=0}^{a^2}\int_{\theta=0}^{2\pi}\int_{r=\sqrt z}^a r\,dr\,d\theta\,dz
$$
$$
=\int_{z=0}^{a^2}\int_{\theta=0}^{2\pi}\left[\frac{r^2}2\right]_{r=\sqrt z}^a\,d\theta\,dz
$$
$$
=\int_{z=0}^{a^2}\int_{\theta=0}^{2\pi}\left(\frac{a^2-z}{2}\right)\,d\theta\, dz
$$
$$
=\int_{z=0}^{a^2} \pi (a^2-z)dz
$$
$$
=\left[\pi\left(a^2z-\frac{z^2}{2}\right)\right]^{a^2}_{z=0}
$$
# Section 6: Integration over surfaces
The Flux integral of a vector field $v$  through a surface S is
$$
\huge\boxed{\int\int_S\vec v\cdot d\vec A=\int\int_S \vec v\cdot \hat n dA}
$$
where $dA$ is an infinitesimal piece of area of the surface and $\hat n$ is the unit normal. 

**Worked Example 6.1**
$$
S:\begin{cases} y=x\\ 0\le x\le 2\\ 0\le z\le 3\end{cases}
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231110152246.png|250]]

So the flux 
$$
\text{FLUX}=\int\int_S\vec v\cdot\vec n dA
$$
From the given, 
$$
\vec v=(3z^2, 6, 6xz)
$$
If we take a perpendicular vector (cross product) away from the surface, then we can get the formula for the normal $\vec n$.
$$
\vec n=(1,1,0)\times (0,0,1)=(1,-1,0)
$$
Normalizing the normal
$$
\vec{\hat n}=\frac{1}{\sqrt 2}(1,-1,0)
$$
Parameterize your variables
$$
\begin{cases} x=y=\frac{u}{\sqrt 2},\,\,\,\,\, \text{and }u=x\sqrt 2\\ z=v\end{cases}
$$
So, 
$$
dA=du\, dv
$$
$$
\text{FLUX}=\int_{v=0}^3\int_{u=0}^{2\sqrt 2} (3v^2,6,\frac{6uv}{\sqrt 2})\cdot \frac{1}{\sqrt 2}(1,-1,0)\,\, du\, dv
$$

$$
=\int_{v=0}^3\int_{u=0}^{2\sqrt 2} \left(\frac{3v^2}{\sqrt 2}-\frac{6}{\sqrt 2}\right)\, du\, dv
$$

**Worked Example 6.3**
$$
x=y=\frac{u}{\sqrt 2};\,\,\,\,\,\, z=v
$$
$$
\vec r(u,v)=\left(\frac{u}{\sqrt 2}, \frac{u}{\sqrt 2}, v\right)
$$
This parametric form is identical to the Example 6.1.
$$
d\vec A=\left(\frac{\partial \vec r}{\partial u}\times \frac{\partial \vec r}{\partial v}\right) du\, dv
$$
$$
=\left(\frac{1}{\sqrt 2},\frac{1}{\sqrt 2},0\right)\times \left(0,0,1\right)\, du\, dv
$$
$$
=\frac{1}{\sqrt 2}\left(1,-1,0\right)\, du\, dv
$$

