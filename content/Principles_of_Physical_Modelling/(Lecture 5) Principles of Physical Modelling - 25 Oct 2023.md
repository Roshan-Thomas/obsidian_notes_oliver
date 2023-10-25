---
title: Lecture 5
date: 25 Oct 2023
---
## Example

We have a slope at angle $\beta$ and we have a block on the slope that is going to slide down. The coefficient of friction is $\mu$. Lets take the coordinate axis $\vec i$ horizontal to the slope and the $\vec j$ axis perpendicular to the slope.  Use Lagrangian mechanics to model the system.

![[Principles_of_Physical_Modelling/images/Pasted-image-20231025090451.png|400]]

We have *1 degree of freedom/generalized coordinate $x$*
### Kinetic Energy T (since $\vec\omega=0$)
$$
T=\frac{1}2 m|\vec v|^2=\frac{1}2 m\dot x^2,\,\,\,\,\,\,\,\,\, \vec v=\dot x\vec i
$$

### Potential Energy U
$$
U=-m(\vec g\cdot\vec r_c)
$$
If we parameterize the block into into corresponding components you get $g\sin\beta$ in the downward direction and $g\cos\beta$ in the perpendicular direction.
![[Principles_of_Physical_Modelling/images/Pasted-image-20231025090852.png|400]]
$$
U=-m(g\sin\beta\vec i-g\cos\beta\vec j)\cdot c\vec i
$$
$$
=-mg\sin\beta x
$$
The Lagrangian
$$
L=T-U=\frac 1 2 m\dot x^2+mgx\sin\beta
$$
### Friction
$$
\vec F_f=-|\vec F_f|\vec i
$$
Lets draw a free-body diagram showing the forces acting on the block
![[Principles_of_Physical_Modelling/images/Pasted-image-20231025091416.png|300]]
$$
\vec W=mg\sin\beta\vec i-mg\cos\beta\vec j,\,\,\,\, \vec N=|\vec N|\vec j
$$
As we balance the forces
$$
\vec W+\vec N+\vec F_f=0
$$
$$
mg\sin\beta\vec i-mg\cos\beta\vec j+|\vec N|\vec j-|\vec F_f|\vec i=0
$$
If the above equation is equal to zero, then taking the individual components
**In the $\vec i$ direction**
$$
mg\sin\beta-|\vec F_f|=0\implies |\vec F_f|=mg\sin\beta
$$
**In the $\vec j$ direction**
$$
-mg\cos\beta+|\vec N|=0\implies |\vec N|=mg\cos\beta
$$
**Friction**
$$
\vec F_f=-\mu|\vec N|\text{ sign}(\dot{\vec x})\vec i=-\mu|\vec N|\vec i=-\mu mg\cos\beta\vec i
$$
where $\text{sign}=\begin{cases}+\\ -\end{cases}$
$$
Q=\vec F_f\cdot\frac{\partial r_c}{\partial q}=\vec F_f\cdot\frac{\partial x}{\partial x}\vec i=-\mu mg\cos\beta\vec i\cdot\vec i=-\mu mg\cos\beta
$$
### Equation of Motion
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot q}\right)-\frac{\partial L}{\partial q}=Q
$$
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial\dot x}\right)-\frac{\partial L}{\partial x}=-\mu mg\cos\beta
$$
$$
\huge\boxed{m\ddot x-mg\sin\beta=-\mu mg \cos\beta}
$$
____
## Example
We have a disk that is rolling down a hill, but this disk might slip while rolling down. The slope has an angle of $\beta$. The rolling direction is x (parallel to the slope) and the angle of rotation is given as $\phi$. Here gravity is taken as $g$ 
![[Principles_of_Physical_Modelling/images/Pasted-image-20231025093601.png|400]]

We need *two generalized constants* as the disc can slop $q_1=x,\,\,\,\, q_2=\phi$
### Kinetic Energy
$$
T=\frac{1}2 m|\vec v_c|^2+\frac{1}2 I_C|\vec\omega|^2
$$
Since we are interested in the kinetic energy at the center of mass, then $A\equiv C$, $\vec r_{AC}=0$.
$$
\vec r_C=x\vec i,\,\,\,\, \vec v_C=\dot x\vec i
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231025094503.png|300]]

We have taken $\vec\omega$ rotating in the clockwise direction, and $\phi$ is measured clockwise.
$$
\vec\omega=-\dot\phi\vec k,\,\,\,\,\,\,|\vec\omega|^2=\dot\phi^2
$$
### Potential Energy
$$
U=-m(\vec g\cdot\vec r_C)=-mg\sin\beta x\,\,\,\,\,\,\text{ (as before)}
$$
### Friction
$$
Q_1=\vec F_f\cdot\frac{\partial\vec v}{\partial\dot x}
$$
where,
$$
\vec v_p=\vec v_C+\vec\omega\times\vec r_{CA}=\dot x\vec i+(-\dot\phi\vec k)\times(-R\vec j)
$$
$$
\vec v_p=(\dot x-\dot\phi R)\vec i
$$
$$
\vec F_f=\begin{cases}-|\vec F_f|\vec i&\text{if disc slips and rotates anti-clockwise}\\ +|\vec F_f|\vec i&\text{if disc slips and rotates clockwise}\end{cases}
$$
So, 
$$
Q_1=\pm|\vec F_f|\vec i\cdot\vec i=\pm|\vec F_f|
$$
$$
Q_2=\vec F_f\cdot\frac{\partial\vec v_p}{\partial\dot\phi}=\pm|\vec F_f|\vec i\cdot(-R\vec i)
$$
$$
Q_2=\mp|\vec F_f|R
$$
**The Lagrangian**
$$
L=T-U=\frac{1}2 m\dot x^2+\frac{1}2 I_c\,\dot\phi^2+mgx\sin\beta
$$
### Equations of Motion
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot x}\right)-\frac{\partial L}{\partial x}=Q_1\implies m\ddot x-mg\sin\beta=\pm |\vec F_f|
$$
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial\dot\phi}\right)-\frac{\partial L}{\partial \phi}=Q_2\implies I_c\, \ddot\phi=\mp |\vec F_f|R
$$
### Case: Not slipping
$$
v=\omega R\implies \dot x=\dot\phi R\implies\vec v_p=0\,\,\,\,\,\,\text{(zero velocity point)}
$$
$$
\implies Q_1=Q_2=0
$$
$$
\dot x=\dot\phi R\implies\ddot x=\ddot\phi R
$$
We have only one degree of freedom.

Applying in the Lagrangian
$$
L=\frac{1}2m\dot x^2+\frac{1}2 I_c\,\dot\phi^2+mgx\sin\beta=\frac{1}2 m\dot x^2+\frac{1}2 I_c\frac{\dot x^2}{R^2}+mgx\sin\beta
$$
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial\dot x}\right)-\frac{\partial L}{\partial x}=0\implies\frac{d}{dt}\left(m\dot x+\frac{I_c}{R^2}\dot x\right)-mg\sin\beta=\left(m+\frac{I_c}{R}\right)\ddot x-mg\sin\beta=0
$$
$$
\implies \ddot x=\cfrac{mg\sin\beta}{\left(m+\frac{I_c}{R^2}\right)}
$$
$$
I_c=\begin{cases}\frac{1}2 mR^2,&\text{solid disk}\\ mR^2,&\text{ring}\end{cases}
$$
#### Solid Disc
$$
\ddot x=\cfrac{mg\sin\beta}{m+\frac{1}2 m}=\frac{2}3 g\sin\beta\leftarrow\text{ full can, faster}
$$
#### Ring
$$
\ddot x=\cfrac{mg\sin\beta}{m+m}=\frac{1}2 g\sin\beta\leftarrow\text{ empty can, slower}
$$
### When the disc is Slipping 
From Coulomb's Law
$$
\vec F_f=-\mu \,mg\cos\beta\text{ sign}(\dot x-R\dot\phi)\vec i
$$
So,
$$
m\ddot x-mg\sin\beta=-\mu\, mg\cos\beta\text{ sign}(\dot x-R\dot\phi)
$$
Rearranging,
$$
\implies m\ddot x=mg\sin\beta-\mu\,mg \cos\beta\text{ sign}(\dot x-R\dot\phi)
$$
$$
\ddot x=g\sin\beta\left(1-\mu\cot\beta\text{ sign}(\dot x-R\dot\phi)\right)
$$
If the can goes faster than the rolling can, then,
$$
1-\mu\cot\beta\text{ sign}(\dot x-R\dot\phi)>\frac{2}3
$$
$$
\implies\mu\cot\beta\text{ sign}(\dot x-R\dot\phi)<\frac 1 3
$$
$$
\implies\tan\beta > 3\mu\text{ sign}(\dot x-R\dot\phi)
$$
If $\dot x<R\dot\phi\implies\text{ sign}(\dot x-R\dot\phi)=-1$, slipping clockwise, $\underbrace{\tan\beta>-3\mu}_{\text{always true}, \forall\,\beta\,\,\in[0,\frac\pi2)}$   
If $\dot x>R\dot\phi\implies \text{ sign}(\dot x-R\dot\phi)=1$, slipping anti-clockwise

- faster $\tan\beta>3\mu$

- for wood $\mu=0.33$, $\tan^{-1} (0.99)\cong \tan^{-1}(1)$ 
