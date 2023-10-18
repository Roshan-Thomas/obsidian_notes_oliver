---
title: Lecture 4
date: 18 Oct 2023
---

- In a rigid body, two particles will ALWAYS be the same distance away from each other, no matter how you rotate the body.
- But, in a fluid, two particles need not be the same distance from each other, when the body is rotated.

Let's model a rigid body using Lagrangian, with a center of mass near the origin, which has a length of $a$ and width $b$. It is placed in the XY plane as indicated by the $\vec i$ and $\vec j$ coordinates. 

Point $A$ (not on the image) on the left top-most corner is where there will be a hole.
![[Principles_of_Physical_Modelling/images/Pasted-image-20231018090610.png|400]]

The center of mass of this body would be $\vec r_1=(0,0)$ 
The mass $m_1=\rho ab$
$\text{uniform }\equiv\text{ constant density}$

Dimensions $[M]=[ML^{-2}][L][L]$

where $\rho$ is the area density $(kg/m^2)$

The Moment of Inertia about the center of mass of a rectangle of mass $m_1$ and sides $a$ and $b$ 
$$
I^o=\frac{1}{12}m_1(a^2+b^2)
$$

When we cut out a portion of the above rectangle at the center, the center of mass changes to the midpoint along the Y axis known as point $B$. The length is $\frac{b}2$ and width is $\frac{h}2$.
![[Principles_of_Physical_Modelling/images/Pasted-image-20231018091505.png|400]]

Center of mass $\vec r_2=\frac{b}4\vec j$

Mass $m_2=\rho\frac{b^2}4$

Moment of Inertia of this new object
$$
I_2^B=\frac{1}{12}m_2\left(\frac{b^2}4+\frac{b^2}4\right)
$$
$$
I_2^B=\frac{1}{24}m_2\, b^2
$$
Dimensions $[ML^2]$

The original rectangle body would look like the image below once the mini-rectangle is cut-out.
![[Principles_of_Physical_Modelling/images/Pasted-image-20231018091927.png|400]]

Mass $m=m_1-m_2$

$$
m=\rho\left(ab-\frac{b^2}4\right)
$$

**Center of Mass**
$$
\vec r_{oc}=\cfrac{\displaystyle\sum_{i=1}^n \vec r_i\, m_i}{\displaystyle\sum_{i=1}^n m_i}=\frac{\vec r_1m_1-\vec r_2m_2}{m_1-m_2}
$$
$$
=\cfrac{\dbinom{0}{a}\rho\, ab-\dbinom{0}{\cfrac{b}4}\rho\, \frac{b^2}4}{\rho\left(ab-\frac{b^2}4\right)}=\frac{-b^2}{16a-4b}\vec j
$$
We can use the Parallel Axis Theorem to move the Moment of Inertia to another point (which is not the Center of Mass)

**Moment of Inertia about (0,0)=0**
$$
I_3^o=I_1^o-I_2^o
$$
By the Parallel Axis Theorem
$$
I_2^o=I_2^b+m_2|\vec r_{ob}|^2
$$
$$
=\frac{1}{24}m_2b^2+\rho\frac{b^2}4\left(\frac{b}4\right)^2=\frac{1}{24}\left(\rho\frac{b^2}4\right)+\rho\frac{b^4}{64}
$$
$$
I_2^o=\frac{5}{192}\rho\, b^4
$$
So, 
$$
I_3^o=I_1^o-I_2^o
$$
$$
=\frac{1}{12}\rho ab(a^2+b^2)-\frac{5}{192}\rho\, b^4
$$
**Moment of Inertia about A**

By using the Parallel Axis Theorem
$$
I_3^a\ne I_3^o+m|\vec r_ao|^2
$$
The above equation is not equal as 0 is not the center of mass of the third body.
$$
I_3^o=I_3^c+m|\vec r_{oc}|^2\implies I_3^c=I_3^o-m|\vec r_{oc}|^2
$$
$$
I_3^A=I_3^c+m|\vec r_{ac}|^2=I_3^o-m|\vec r_{oc}|^2+m|\vec r_{ac}|^2=I_3^0+m(|\vec r_{ac}|^2-|\vec r_{oc}|^2)
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231018094721.png]]
So,
$$
I_3^a=\frac{1}{12}\rho\, ab(a^2+b^2)-\frac{5}{192}\rho\, b^4+\rho\left(ab-\frac{b^2}{4}\right)(\,\,\,\,\,\,\,\,\,\,\,\,)
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231018095230.png|400]]

Note: The width should is $b/2$ and length should is $a/2$. 
$$
|\vec r_{ac}|^2=\left(\frac{b}2\right)^2+\left(\frac{a}2+\frac{b^2}{16a-4b}\right)^2
$$
Assume $a=2b$
$$
|\vec r_{ac}|^2=\frac{1009}{784}b^2
$$
So,
$$
I_3^a=\frac{587}{192}\rho b^4
$$
Dimensions $[ML^2]=[ML^{-2}][L^4]$

**Dynamics Swinging about A**

The rigid body is swinging about point $A$ by an angle $\theta$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231018100545.png|500]]

**Kinetic Energy (T)**

Since $\vec v_a=0$ then,
$$
T=\frac{1}2 I_3^a|\vec\omega|^2
$$
where $|\vec\omega|=\dot\theta$
$$
T=\frac{587}{384}\rho\, b^4\dot\theta^2
$$
Dimensions $[ML^{-2}][L^4][T^{-1}]^2=[ML^2T^{-2}]$
$$
\left(\frac{1}2 mv^2=M(LT^{-1})^2=ML^2T^{-2},\,\,\,\, F\times d=Nm=[MLT^{-2}][L=ML^2T^{-2}]\right)
$$
**Potential Energy (U)**

![[Principles_of_Physical_Modelling/images/Pasted-image-20231018101413.png|300]]

We have
$$
\left(\vec r_{oc}=-\frac{b}{28}\vec j\right)
$$
As $a=2b$
$$
\vec r_{ac}=\vec r_{ap}+\vec r_{pc}
$$
$$
\vec r_{ap}=b\cos\theta\vec i-b\sin\theta\vec j
$$
$$
\vec r_{pc}=-\frac{15}{28}b\sin\theta\vec i-\frac{15}{28}\cos\theta\vec j
$$
$$
\vec r_{ac}=\left(b\cos\theta-\frac{15}{28}b\sin\theta\right)\vec i-\left(b\sin\theta+\frac{15}{28}b\cos\theta\right)\vec j
$$
Potential Energy
$$
U=-m\left(\vec g\cdot\vec r_{ac}\right)=-mg\left(b\sin\theta+\frac{15}{28}b\cos\theta\right)
$$
$$
U=-\frac{7}4\rho\, gb^3\left(\sin\theta+\frac{15}{28}\cos\theta\right)
$$
Dimensions $[ML^{-2}][LT^{-2}][L^3]=[MLT^{-2}]$ 


**Lagrangian**
$$
L=T-U=\frac{587}{384}\rho b^4\dot\theta^2+\frac{7}4\rho gb^3\left(\sin\theta+\frac{15}{28}\cos\theta\right)
$$
**Equation of Motion**
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot\theta}\right)-\frac{\partial L}{\partial\theta}=0
$$
$$
\implies\frac{587}{192}\rho\, b^4\ddot\theta-\frac{7}4\rho\, gb^3\left(\cos\theta-\frac{15}{28}\sin\theta\right)=0
$$
$$
\implies \ddot\theta-\frac{336}{587}\frac{g}b\left(\cos\theta-\frac{15}{28}\sin\theta\right)=0
$$
**Equilibrium Points**
$$
\frac{\partial L}{\partial\theta}=0\implies\cos\theta=\frac{15}{28}\sin\theta=0\implies\tan\theta=\frac{28}{15}
$$
$$
\theta_1^*=61.8^o\,\,\, \text{ or }\theta_2^*=241.8^o
$$
**Stability**
$$
k=-\frac{\partial^2L}{\partial\theta^2}=-\frac{7}4\rho\, gb^3\left(-\sin\theta-\frac{15}{28}\cos\theta\right)=\frac{7}{4}\rho\,gb^3\left(\sin\theta+\frac{15}{28}\cos\theta\right)
$$
$$
\begin{align*}k\Bigg\vert_{\theta_1^*}>0&\implies\text{ stable}\\ k\Bigg\vert_{\theta_2^*}<0&\implies\text{ unstable}\end{align*}
$$
**Linearized Equation of Motion**
$$
M=\frac{\partial^2L}{\partial \dot\theta^2}=\frac{587}{192}\rho b^4
$$
$$
\ddot\theta+0.79\frac{g}{b}\theta=0
$$
$$
\theta=A\sin\left(\sqrt{\frac{0.79 g}{b}}t\right)+B\cos\left(\sqrt{\frac{0.79g}b}t\right)
$$
**Check this Experimentally**

$b=0.07m$, 
$\omega=\sqrt{\frac{0.79\times9.8}{0.07}}=10.5\,\text{rad/s}$ (angular frequency)

The natural frequency
$$
f=\frac{\omega}{2\pi}=1.67\,\text{Hz}
$$
The time period
$$
T=\frac{1}{f}=0.6\text{ seconds}
$$
From the video 
$$
T=\frac{2.55}{4}=0.64\text{ seconds}
$$
The slight error could be due to human error, or because our calculation is for linear systems but the motion is non-linear due to friction, air-resistance etc. 

From photo
$$
\theta_1^*=57^o\,\,(\text{as compared to }61.8^o)
$$

