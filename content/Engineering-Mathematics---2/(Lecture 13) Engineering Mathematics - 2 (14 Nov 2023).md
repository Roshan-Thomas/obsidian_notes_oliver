---
title: Lecture 13
date: 14 Nov 2023
---
# About the normal vector $\vec n$ for surfaces
- Positive $\vec n$ when pointing out of a surface
- If the surface is a plane,
	- Positive normal will be described
	- Example: Pointing at positive z-axis
- Sometimes $\vec n$ can be normalized
$$
\vec{\hat n}=\frac{\vec n}{|\vec n|}
$$
**Example**
$$
\vec n=(a\cos\theta, a\sin\theta, 0)
$$
$$
|\vec n|=\sqrt{a^2\cos^2\theta+a^2\sin^2\theta}=a
$$
$$
\rightarrow \vec{\hat n}=\frac{\vec n}{|\vec n|}=(\cos\theta,\sin\theta,0)
$$
But
$$
\vec n=(a\cos\theta,a\sin\theta,\rho)
$$
$$
|\vec n|=\sqrt{a^2+\rho^2}
$$
$$
\rightarrow \vec{\hat n} = \frac{\vec n}{|\vec n|}=\frac{1}{\sqrt{a^2+\rho^2}}
$$
This is hard to calculate in the integral, so for the exam, the professor will tell you beforehand if you have to normalize the normal or not. 
___

**Worked Example 6.4**

Find the flux of the vector field
$$
\vec v=\frac{1}{16}(x^2+y^2)\vec i+\frac{xy}{8}\vec j+x\vec k
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231114152119.png|400]]

$$
\begin{cases}=x=r\cos\theta\\ y=r\sin\theta\\ z=z\end{cases}
$$
(i) the curved surface

Parameterize $S_1$
$$
\begin{cases} x=4\cos\theta\\ y=4\sin\theta\end{cases}
$$
$$
\vec r(\theta, z)=(4\cos\theta, 4\sin\theta, z)
$$
$$
\int\int\vec v\cdot dA=\int\int\vec v\cdot \vec n dA
$$
$$
dA=\frac{\partial \vec r}{\partial \theta}\times\frac{\partial \vec r}{\partial z}\, d\theta\, dz
$$
$$
=(-4\sin\theta, 4\cos\theta, 0)\times(0,0,1)
$$
$$
=\underbrace{(4\cos\theta, 4\sin\theta,0)}_{} d\theta\, dz
$$
$$
=4(\cos\theta, \sin\theta, 0)\, d\theta\, dz
$$
So,
$$
\int\int_{S_1}\vec v\cdot d\vec A=\int_{z=0}^1\int_{\theta=0}^{2\pi}(\cos^2\theta-\sin^2\theta, 2\sin\theta\cos\theta, 4\cos\theta)\cdot (4\cos\theta, 4\sin\theta,0)\, d\theta\, dz
$$
$$
=\int\int 4\cos\theta\underbrace{(\sin^2\theta+\cos^2\theta)}_{1} \, d\theta\,d z
$$
$$
=\left[z\right|_0^1\underbrace{\int_0^{2\pi} 4\cos\theta\, d\theta}_{0}=0
$$
(ii) Parameterize the disc

![[Engineering-Mathematics---2/images/Pasted-image-20231114153700.png|400]]
$$
\begin{cases}x=4\cos\theta&\implies r\cos\theta\\ y=4\sin\theta&\implies r\sin\theta\\ z=z&\implies 1\end{cases}
$$
$$
\vec r(r,\theta)=(r\cos\theta, r\sin\theta,1),\,\,\,\,\,\,\,\,\, \text{where }0\le r\le 4,\, 0\le \theta\le 2\pi
$$
$$
d\vec A=\frac{\partial \vec r}{\partial r}\times\frac{\partial \vec r}{\partial \theta}\, dr\, d\theta
$$
$$
=(\cos\theta, \sin\theta,0)\times (-r\sin\theta, r\cos\theta, 0)\, dr\, d\theta
$$
$$
=(0,0,r)\, dr\, d\theta
$$
$$
=(0,0,1)\, r\, dr\, d\theta
$$
$$
\int\int \vec v\cdot d\vec A=\int\int\vec v\cdot \hat z\, r\, dr\, d\theta
$$
$$
=\int\int \cancel{r^2\cos\theta\, dr\, d\theta}^{\, 0}=0
$$
___
# Section 7.2 - Stoke's Law 
$$
\int\vec F\cdot d\vec r=\int\int (\vec \nabla\times \vec F)\cdot d\vec A
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231114154832.png|300]]
$$
\begin{cases}\vec F=(y, z, x)\\ z=1-(x^2+y^2)\end{cases}
$$
- $C\rightarrow\text{ Circle to }z=0$, $x^2+y^2=1$
$$
\vec r_C(t)=(\cos t,\sin t,0),\,\,\,\,\,\,\,\,\,\,\, t\,\epsilon\,[0,2\pi]
$$
- $S$ Paraboloid
$$
z=f(x,y)=1-(x^2+y^2),\,\,\,\,\,\,\,\,\,\,\,\,\, z\ge 0
$$
$$
\begin{rcases}x=\rho\cos\theta\\ y=\rho\sin\theta\end{rcases}\,\,\,\, z=1-\rho^2
$$
$$
\vec r_s(\rho,\theta)=(\rho\cos\theta,\rho\sin\theta,1-\rho^2)\,\,\,\,\,\,\,\, 0<\theta<2\pi,\,\, 0\le\rho\le 1
$$



