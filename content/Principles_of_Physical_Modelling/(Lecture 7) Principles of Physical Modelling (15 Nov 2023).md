---
title: Lecture 7
date: 15 Nov 2023
---
# Conservation Laws
1. Identify conservation law (mass, momentum, energy)
2. Construct conservation equation, $\frac{dM}{dt}=R$
$$
\rightsquigarrow \text{Relates some 'density' to 'flux'}
$$
3. Specify constitutive relation between density and flux.

*Side note: To solve an equation such as $\frac{\partial Q}{\partial t}+\frac{\partial}{\partial x}(\rho u)=0$, we can use the 'Method of characteristics' method. Notes for this can be found on Blackboard if it piques your interest.*

## One-dimensional diffusion
Imagine we have a bunch of particles from length $a$ to $b$ in one dimension, as shown in image. We can use the above three steps in conservation laws to model the system.   
![[Principles_of_Physical_Modelling/images/Pasted-image-20231115091438.png|500]]

Step 1:
"Density" $\backsim$ concentration, C which is the "number of particles per length"
where $C=C(x,t)$ (is a function of space and time).
$$
M(t)=\int_a^b C\,\, dx
$$
Rate of change of $M$
$$
\begin{rcases}\cfrac{dM}{dt}=J(a,t)-J(b,t)\\[0.5em] =-\displaystyle\int_a^b \frac{\partial J}{\partial x}\, dx\end{rcases}\text{ integral form}
$$
Step 2:
$$
\int_a^b\left(\frac{\partial C}{\partial t}+\frac{\partial J}{\partial x}\right)\, dx=0
$$
Step 3:
$$
\rightsquigarrow \boxed{\frac{\partial C}{\partial t}+\frac{\partial J}{\partial x}=0}
$$
$$
\rightsquigarrow \boxed{J=J(C,\frac{\partial C}{\partial x},\frac{\partial C}{\partial t},\dots)}
$$

# Fick's Law (1885) or Fourier's Law
Fick did an experiment where he used salt solutions and worked out the rate of change of concentration and change in flux. 
$$
J=-D\frac{\partial C}{\partial x}
$$
The above equation means that 'stuff moves from higher to lower concentration'.
$$
\boxed{\frac{\partial C}{\partial t}=-\frac{\partial J}{\partial x}=D\frac{\partial ^2C}{\partial x^2}} \backsim \text{Diffusion equation}
$$
Note: Fourier's Law is similar to Fick's Law where it describes how temperature goes from hot areas to cold.
$$
J=-k\frac{\partial T}{\partial x}
$$
## Initial and boundary conditions
$$
C(x,0)=C_0(x) \backsim \text{initial condition}
$$
$$
C(x_1, t)=C_1,C(x_2, t)=C_2(t)\backsim\text{boundary condition}
$$
**Example**
$$
C(x,0)=C_0(x)
$$
$$
C\rightarrow 0\text{ as }x\rightarrow \pm 0
$$
## Solving the diffusion equation
Covered in Eng. Maths 2
- Separation of variables (infinite domain e.g. $x_1=0, x_2=1$)
- Similarity solutions ($x_1=0, x_2=\infty$)
- Fourier transform (Week 10 of Eng. Maths 2) ($x_1=-\infty, x_2=\infty$)

Definition: 
$$
C(k,t)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty c(x,t)e^{-ikx}\, dx=F(x)
$$
which is the Fourier transform of C
$$
c(x,t)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty C(k,t)e^{+ikx}\, dk
$$
which is the inverse Fourier transform of c

To make life more easier, let $\frac{\partial C}{\partial t}=C_t$, so
$$
C_t=DC_{xx}
$$
Multiplying both sides by $e^{-ikx}$ and integrate both sides from $-\infty$ to $\infty$
$$
\int_{-\infty}^\infty C_t\, e^{-ikx}\, dx=D\int_{-\infty}^\infty C_{xx}\, e^{-ikx}\, dx
$$
$$
\frac{\partial}{\partial t}\int_{-\infty}^\infty C\, e^{-ikx}\, dx=D\left\{[C_x\, e^{-ikx}]_{-\infty}^\infty +ik\int_{-\infty}^\infty C_x\, e^{-ikx}\, dx\right\}
$$
By the boundary conditions
$$
\frac{\partial C}{\partial t}=ikD\left\{[Ce^{-ikx}\, dx]_{-\infty}^\infty+ik\int_{-\infty}^\infty C\, e^{-ikx}\, dx\right\}
$$
$$
\boxed{\frac{\partial C}{\partial t}=-Dk^2\, C}\,\,\text{(big C)}
$$
Also,
$$
\boxed{C(k,0)=C_0(k)}\,\,\,\text{(initial conditions)}
$$
Solution:
$$
C=C_0(k)e^{-Dk^2\, t}
$$
$$
c(x,t)=\frac{1}{\sqrt{2\pi}}\int C\,e^{ikx}\, dk=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty C_0(k)\, e^{-Dk^2t}\, dk
$$
Result: (don't worry)
$$
F\left(\frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty a(s)b(x-s)ds\right)=A(k)B(k)
$$
So we can show
$$
c(x,t)=\frac{1}{2\sqrt{\pi Dt}}\int_{-\infty}^\infty C_0(s)\text{exp}\left[-\frac{(x-s)^2}{4Dt}\right] ds
$$
Simple $C(x,0)=\delta(x)$
	Note: The $\delta(x)$ function is 1 at zero, and zero every where else.
$$
\int_{-\infty}^\infty \delta(s)f(x-s)ds
$$
$$
\rightsquigarrow\int_{-\infty}^\infty \delta(x-s)f(s)\,ds=f(x)
$$
So the final solution is
$$
\boxed{C(x,t)=\frac{1}{2\sqrt{\pi D t}}e^{-\cfrac{-x^2}{4Dt}}}
$$
# Three-dimensional case
$$
\frac{\partial Q}{\partial t}+\nabla\cdot \vec J=0
$$
where 
$$
\nabla\cdot \vec J=\frac{\partial J_x}{\partial x}+\frac{\partial J_y}{\partial y}+\frac{\partial J_z}{\partial z}
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231115104718.png|400]]

And,
$$
\rho=\rho_m\, c_p\, T(x,t)
$$
$$
\vec J=-k\nabla T\,\,\,\,\,\text{(Fourier's Law)}
$$
$$
\rho_m c_p\frac{\partial T}{\partial t}=-\nabla\cdot(-k\nabla T)=k\nabla^2 T
$$
where
$$
\nabla^2=\frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2}
$$
