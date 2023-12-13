---
title: Lecture 10
date: 13 Dec 2023
---
# Exam Instructions
- Section A 
	- The questions goes in the order the professor taught the material in.


# Mock Question Paper Q3
![[Principles_of_Physical_Modelling/images/Pasted-image-20231213091231.png|500]]

**Part (a)** 

**(i)**

Mass of the disc $M_{\text{disc}}=\text{Area }\times\text{Density }=\pi R^2\rho_{\text{disc}}=\pi R^2\frac{1}{\pi}=R^2\, kg$
Mass of the square $M_{\text{sq}}=a^2\times\text{ density}=\left(\frac{R}{2}\right)^2\times 1=\frac{R^2}4\, kg$
$$
\vec r_{OC}=\frac{M_{\text{disc}}\vec r_c^{\text{ disc}}+M_{\text{sq}}\vec r_c^{\text{ sq}}}{M_{\text{disc}}+M_{\text{sq}}}=\frac{4}{5R^2}\frac{R^3}{8}\vec j=\frac{R}{10}\vec j
$$
$$
\vec r_C^\text{ disc}=\vec o,\,\,\,\,\,\, \vec r_C^\text{ sq}=\frac{R}2\vec j
$$

**(ii)**

$$
I_C=I_C^\text{ disc}+I_C^{\text{ sq}}
$$
$$
=\left(I_0^\text{ disc}+M_{\text{disc}}|\vec r_{oc}|^2\right)+\left(I_A^{\text{ sq}}+M_{\text{sq}}|\vec r_{AC}|^2\right)\tag{Parallel Axis Theorem}
$$
$$
=\left(\frac{1}2 M_{\text{disc}}R^2+M_{\text{disc}}\left(\frac{R}{10}\right)^2\right)+\left(\frac{1}6 M_{\text{sq}}\left(\frac R 2\right)^2+M_\text{sq}\left(\frac 2 5 R\right)\right)
$$
$$
=\left(\frac 1 2 R^2\times R^2+R^2\left(\frac{R^2}{100}\right)\right)+\left(\frac{1}6 \frac{R^2}4\frac{R^2}4+\frac{R^2}4\left(\frac{4}{25}R^2\right)\right)
$$
$$
=\left(\frac 1 2+\frac 1{100}+\frac{1}{96}+\frac{1}{25}\right)R^4
$$
$$
=\frac{269}{430}R^4
$$

**Part (b)**

**(i)**

![[Principles_of_Physical_Modelling/images/Pasted-image-20231213093332.png|400]]

$$
\vec r_{OC}=\frac{R}{10}\left(\cos\phi\vec i+\sin\phi\vec j\right)
$$
$$
U=-m(\vec g\cdot \vec r_{OC})=-(M_\text{disc}+M_{\text{sq}})\left(-g\vec j\cdot\left(\frac{R}{10}\left(\cos\phi\vec i+\sin\phi\vec j\right)\right)\right)
$$
$$
U=+\frac{5R^2}{4}g\frac{R}{10}]\sin\phi=g\frac{R^3}8\sin\phi
$$

**(ii)**

$$
\vec v_C=\vec v_P+\vec \omega\times \vec r_{PC}=\vec O+\omega \vec k\times (\vec r_{PO}+\vec r_{OC})
$$
$$
=\dot\phi\vec k\times\left(R\vec j+\frac{R}{10}\left(\cos\phi\vec i+\sin\phi\vec j\right)\right)
$$
$$
=\dot\phi\left(-R\vec i+\frac{R}{10}\left(\cos\phi\vec j-\sin\phi\vec j\right)\right)
$$
$$
\vec v_C=-\dot\phi\left(R+\frac{R}{10}\sin\phi\right)\vec i+\frac{\dot\phi R}{10}\cos\phi\vec j
$$
The kinetic equation
$$
T=\frac 1 2 m|\vec v_C|^2+\frac 1 2 I_C|\vec w|^2
$$
$$
=\frac 1 2\left(\frac{5}{4}R^2\right)\left(\dot\phi^2\left(R+\frac{R}{10}\sin\phi\right)^2+\frac{\dot\phi^2R^2}{100}\cos^2\phi\right)+\frac{1}2\left(\frac{269}{480}R^4\right)\dot\phi^2
$$
$$
T=\frac{R^4\dot\phi^2}{8}\left(\frac{175}{24}+\sin\phi\right)
$$
# Mock Question Paper Q4
**Part (a)**

The dimensions
$[P]=T$
$[M]=M$
$[L]=L$
$[g]=[LT^{-2}]$

$$
[P]=[M]^\alpha [L]^\beta [g]^\gamma
$$
$$
T=M^\alpha L^\beta L^\gamma T^{-2\gamma}
$$
$$
\begin{rcases}\alpha=&0\\-2\gamma=&1\\\beta+\gamma=&0\end{rcases}
$$
$$
\gamma=-\frac 1 2,\,\,\,\,\,\,\,\, \beta=\frac 1 2
$$
The expression
$$
\boxed{P=k_0\sqrt{\frac L g}}
$$
where $k_0$ is a dimensionless proportionality constant.

**Part (b)**

$$
\frac{P}{\sqrt{\frac L g}}=k_0
$$
Take a pendulum of length $L=L^*$ and then measure the period $P=P^\star$ 
$$
k_0=\frac{P^*}{\sqrt{\frac{L^*}g}}=k^*\rightsquigarrow \boxed{P=k_0\sqrt{\frac L g}}
$$

# Mock Question Paper Q6

**Part (a)**

![[Principles_of_Physical_Modelling/images/Pasted-image-20231213103623.png|400]]

A viscous fluid $\rightsquigarrow$ Navier Stokes
$$
\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z}=0
$$
$$
\vec u=(u(z,t),0,0)
$$
$$
\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}+w\frac{\partial u}{\partial z}=-\frac{1}{\rho}\frac{\partial p}{\partial x}+\nu(u_{xx}+u_{yy}+u_{zz})
$$
$$
\frac{\partial u}{\partial t}=\nu\cdot u_{zz}
$$
$$
0=\frac{\partial p}{\partial y}=\frac{\partial p}{\partial z}
$$
$$
\boxed{\frac{\partial u}{\partial t}=\nu\frac{\partial^2 u }{\partial z^2}}
$$

**Part (b)**

$$
u(z,0)=0\tag{initial condition}
$$
No slip condition tells us that $\vec u=\vec u_B$
$$
u(0,t)=U\cos(\Omega t)
$$
$$
u(z\rightarrow\infty, t)=0
$$

**Part (c, d)**

$$
u_t=\nu u_{zz},\,\,\,\,\, u(0,t)=U\cos(\Omega t),\,\,\,\,\, u(z\rightarrow\infty, t)=0
$$
The solution looks like
$$
u=Re\left[Uf(z)e^{j\Omega t}\right]
$$
$$
u_t=Uf(z)j\Omega e^{j\Omega t}
$$
$$
u_{zz}=Uf''(z)e^{j\Omega t}
$$
$$
Uf\, j\Omega e^{j\Omega t}=\nu Uf''(z)e^{j\Omega t}
$$
$$
\rightsquigarrow \boxed{f''(z)-\frac{j\Omega}{\nu}f=0}
$$

The boundary conditions
$$
u(z\rightarrow\infty,t)=0\rightarrow f(z)=0\text{ as }z\rightarrow\infty
$$
$$
U\cos(\Omega t)=U\, Re\left[e^{j\Omega t}\right]
$$
