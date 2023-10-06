---
title: Lecture 4
date: 06 Oct 2023
---
# Force and potential energy
$$
F=\text{grad }V(\vec r)=\vec\nabla V(\vec r)
$$
Force is in the direction of maximum increase in potential.

Examples: 
- Take a spring and stretch it. In the process of stretching it, you are working against a force in the opposite direction, and by that method you are adding energy to the system.
- Electrostatic force $E$ between two particles of charge $Q_1$ and $Q_2$ being the gradient of the electrostatic potential $f$
$$
\vec E=\frac{1}{4\pi\epsilon_0}Q_1Q_2\left(\frac{\vec r}{|\vec r|^3}\right)
$$

**Worked Example:**
A space ship moves in the gravitational field of planet with gravitational potential
$$
\phi=\frac{k}{|r|}
$$
Find the force?

**Solution:**
$$
\phi(x,y,z)=\frac k{|\vec r|}
$$
where $k$ is constant
So, force
$$
\vec F=\vec\nabla\phi=\left(\frac{\partial\phi}{\partial x},\frac{\partial\phi}{\partial y},\frac{\partial\phi}{\partial z}\right)
$$
$$
\phi(x,y,z)=\frac{k}{|\vec r|}=\frac{k}{\sqrt{x^2+y^2+z^2}}=k(x^2+y^2+z^2)^{-\frac{1}2}
$$
$$
\frac{\partial \phi}{\partial x}=-\frac{1}2 k(x^2+y^2+z^2)^{-3/2}\cdot 2x
$$
$$
=-\frac{kx}{|\vec r|^3}
$$
Similarly, $\frac{\partial\phi}{\partial y}=-\frac{ky}{|r|^3}$ and $\frac{\partial\phi}{\partial z}=-\frac{kz}{|\vec r|^3}$
$$
\vec F=\left(-\frac{kx}{|\vec r|^3}, -\frac{ky}{|\vec r|^3}, -\frac{kz}{|\vec r|^3}\right)
$$
$$
=-\frac{k}{|\vec r|^3}(x,y,z)
$$
$$
=-\frac{k\vec  r}{|\vec r|^3}
$$
$$
=-\underbrace{\cfrac{k\overbrace{\hat r}^{\text{direction }\hat r}}{|\vec r|^2}}_{\text{magnitude }\frac{-k}{|\vec r|^2}}
$$
___
In 2D we know that there are 2 kinds of stationary points: Maxima, Minima and Saddles

Note: Hessian will not be tested on the exam.

**Example 2.4** Calculate all the extrema of the following scalar fields
a. $f(x,y)=x^3+y^2-3(x+y)+1$
b. $f(x,y,z)=x^2-3y^2+2z^2+3x+2z+7$

**Solution:**
**Part a**
$$
f(x,y)=x^3+y^2-3(x+y)+1
$$
$$\vec\nabla f=\left(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y}\right)=(2x^2-3, 2y-3)
$$
$$
=0,\,\,\, \text{at stationary points}
$$
$$
\begin{align}3x^2-3=0&\Rightarrow x=\pm 1 \\ 2y-3=0 &\Rightarrow y=\frac{3}2 \end{align}
$$
2 extrema at $(x,y)=(1,\frac{3}2), (-1,\frac{3}2)$

The scalar field is going to change differently in different direction, so we find the following second differentials
$$
\frac{\partial^2 f}{\partial x^2}\,\, \frac{\partial^2 f}{\partial y^2}\,\, \frac{\partial^2 f}{\partial x\partial y}\,\, \frac{\partial^2 f}{\partial y\partial x}
$$
Use the Hessian (contains all the second differentials) to classify type of starting point
$$
H=\begin{pmatrix}\frac{\partial f}{\partial x^2} & \frac{\partial^2f}{\partial x\partial y} \\ \frac{\partial f}{\partial y\partial x} & \frac{\partial f}{\partial y^2}\end{pmatrix}=\begin{pmatrix}6x & 0\\ 0 & 2\end{pmatrix}
$$
So, the eigenvalues are the values on the diagonal of the Hessian
$$
\lambda_1=6x,\, \lambda_2=2
$$
- If both the eigenvalues are negative then its a maxima. 
- If one of them is positive and the other negative then you have a saddle point.
- If both the eigenvalues are positive, then you have a minima

at $(x,y)=(1,\frac 3 2)$ 
$$
\begin{align}\lambda_1=6&>0 \\ \lambda_2=2&>0\end{align}
$$
Therefore its a **minima**

at $(x,y)=(-1,\frac 3 2)$
$$
\begin{align}\lambda_1=-6 &<0 \\ \lambda_2=2&>0 \end{align}
$$
Therefore its a saddle point

**Part b**
$$
f(x,y,z)=x^2-3y^2+2z^2+3x+2z+7
$$
$$
\vec\nabla f=\left(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},\frac{\partial f}{\partial z}\right)=(2x+3,-6y,4z+2)
$$
$$
=0\,\,\, \text{at stationary point}
$$
extremum is $(x,y,z)=\left(\frac{-3}{2},0,-\frac{1}{2}\right)$

The Hessian 
$$
H=\begin{pmatrix}2&0&0\\ 0&-6&0\\ 0&0&4 \end{pmatrix}
$$
$$
\lambda=(2,-6,4)
$$
Therefore, you have a saddle point.