---
title: Lecture 2
draft: false
date: 04 October 2023
---

**Example:** 
On a flat surface, we have a disc that is rotating with angular momentum $\vec\omega_1$ in the clock-wise direction. There is a rod attached to the disk (from the left side), and the rod is resting on a hemi-spherical surface. When the disc starts moving, we need to understand its kinematics. The disc is rolling and its under no-slip conditions. 

The length of the rod is $L$, the point the rod is touching the hemi-spherical surface is marked $B$. The radius of the disc and the radius of the hemi-spherical surface is $R$.

![[Principles-of-Physical-Modelling/images/Pasted-image-20231004090900.png]]

**Solution**
The relative velocity equation 
$$
\vec v_c=\vec v_p+\vec N_1\times \vec r_{pc}
$$
At point $p$ (under the disc) is the zero velocity point, so $\vec v_p=0$

By the right hand rule, $\omega_1$ points towards the page, so 
$$
\vec\omega_1=-\omega_1\vec k, \,\, \omega_1>0
$$
$$
\vec r_{pc}=R\vec v
$$
$$
\vec v_c=v_c\vec i,\,\, v_c>0
$$
Inserting the above equations into the relative velocity equation 
$$
\Rightarrow v_c\vec i=0+(-\omega\vec k)\times(R\vec v)
$$
$$
=\omega R\vec i
$$
So,
$$
v_c=\omega R
$$
The dimensions of the above equation is $[LT^{-1}]=[T^{-1}][L]$, so the dimensions is correct.

The velocity at point $A$
$$
\vec v_A= ?
$$
$$
\vec v_A=\vec v_C+\vec\omega_1\times\vec r_{CA}
$$

$$
=\omega R\vec i+(-\omega_1\vec k)\times(-R\vec i)
$$
$$
=\omega R\vec i+\omega k\vec k=\omega R(\vec i+\vec j)
$$
The velocity at point $B$ 
$$
\vec v_B=\vec v_A+\vec\omega_2\times\vec r_{AB}
$$
$$
\vec\omega_2=\omega_2\vec k
$$
The zero velocity point on a rigid body is perpendicular to the points on the rigid body (point $A$)

![[Principles-of-Physical-Modelling/images/Pasted-image-20231004093949.png]]

$$
\vec v_B=v_B\vec i,\,\,\, v_B>0
$$
$$
\vec r_{AB}=-L\vec i
$$
$$
v_B\vec i=\omega R(\vec i+\vec j)+(\omega_2\vec k)\times(-L\vec i)\vec v_B=v_B\vec i, \,\,\, \vec v_B>0
$$
$$
=\omega R(\vec i+\vec j)-\omega_2\, L\vec j
$$
Equate coefficients
$$
\begin{align}\vec i:&\, v_B=\omega_1 R & \Rightarrow \vec v_{B}=\omega_1\, R\vec i \\\vec j:&\, 0=\omega_1 R-\omega_2\, L & \Rightarrow \omega_2=\omega_1\frac{R}{L}>0 \Rightarrow \vec\omega_2=\omega_1\frac{R}{L}\vec k\end{align}
$$

**Zero velocity point at the rod (Q)**
$$
\vec r_{AQ}=\frac{\vec\omega_2\times \vec V_A}{|\vec\omega_2|^2}=\frac{(\omega_1\frac R L\vec k)\times(\omega_1R(\vec i+\vec j))}{(\vec\omega_1 \frac R L)}=L(-\vec i+\vec j)
$$
**Acceleration at point A** 
$$
\vec a_{A}=\vec a_C +\epsilon_1\times\vec r_{CA}-|\vec \omega_1|^2\vec r_{CA}
$$
where $\epsilon_1$ is the angular acceleration 
$$
\vec a_C=a_C\,\vec i
$$
$$
\epsilon_1=\epsilon_1\vec k
$$
$$
\vec r_{CA}=-R\vec i
$$
$$
|\vec\omega_1|^2=\omega_1^2
$$
Acceleration of point $A$ 
$$
\vec a_{A}=a_C\,\vec i+\epsilon_1\,\vec k\times(-R\vec i)-\omega_1^2(-R\vec i)
$$
$$
=a_C\vec i-\epsilon_1R\,\vec j+\omega_1^2R\,\vec i
$$
$$
=(a_C+\omega_1^2R)\vec i-\epsilon_1\, R\, j
$$
Doing dimensional analysis $[LT^{-2}]=[T^{-1}]^2 L[T^{-2}]L$. So the dimensions are correct on both sides of the equation.
$$
\vec a_A=(a_C+\omega_1^2R)\vec  k+a_C\vec j
$$
**Acceleration at point B, in terms of $a_c,\,v_c,\,R,\,L$**
$$
\vec a_B=\vec a_A+\vec\epsilon_2\times\vec r_{AB}-|\vec\omega_2|^2\vec r_{AB}
$$
We know, 
$$
\vec a_A=(a_c+\omega_1^2R)\vec i+a_c\vec j
$$
$$
v_c=\omega_1R\Rightarrow\omega_1^2\, R=\frac{v_c^2}{R}
$$

$$
\vec a_A=(a_C+\frac{v_c^2}{R})\vec i+a_c\vec j
$$
$$
\vec\epsilon_2=\epsilon_2\vec k=\dot\omega_2\vec k
$$
$$
\omega_2=\omega_1\frac{R}{L}\Rightarrow \dot\omega_2=\dot\omega_1\frac{R}{L}
$$
$$
\epsilon_1=\frac{-a_c}{R}
$$
$$
\vec r_{AB}=-L\vec i
$$
Substituting the above values, the acceleration 
$$
\vec a_B=\left(a_C+\frac{v_c^2}{R}\right)\vec i+a_c\,\vec j+\left(\frac{a_C}{L}k\right)\times(-L\vec i)-\left(\frac{v_C}L)^2(-L\,\vec i\right)
$$
$$
=\left(a_c+\frac{v_C^2}R\right)\vec i+a_C\vec j-a_c\vec j+\frac{v_C^2}{L}\vec i
$$
$$
\vec a_B=\left(a_c+\frac{v_C^2}{R}+\frac{v_C^2}L\right)\vec i
$$
