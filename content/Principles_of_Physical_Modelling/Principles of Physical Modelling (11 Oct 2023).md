---
title: Lecture 3
date: 11 Oct 2023
---
## Example
We have a pendulum with a bob of mass $m$, and its maximum height (in the anti-clockwise direction) it reaches is point $B$. The length of the pendulum is $L$, and it moves by an angle $\theta$, with the gravitational constant of $g$. 

![[Principles_of_Physical_Modelling/images/Pasted-image-20231011091205.png|400]]

### **Solution**
We use Lagrangian method to solve this problem

**Kinetic Energy**
$$
T=\frac{1}2 m|\vec v_B|^2
$$
$$
\vec v_B=\frac{d\vec r_{OB}}{dt}=\vec{\dot r}_{OB}
$$

$$
\vec r_{OB}=L\sin(\theta)\vec i-L\cos(\theta)\vec j
$$
$$
\vec{\dot r}_{OB}=L\dot\theta\cos(\theta)\vec i+L\dot\theta\sin(\theta))\vec j
$$
$$\frac{d}{dt}\sin(\theta(t))=\cos(\theta)\times\frac{d}{dt}(\theta)=\dot\theta\cos\theta\,\,\,\, \text{(Chain rule)}
$$
$$
|\vec v_B|^2=|\vec{\dot r}_{OB}|^2=(L\dot\theta\cos\theta)^2_(L\dot\theta\sin\theta)^2
$$
$$
=L^2\dot\theta^2\cos^2\theta+L^2\dot\theta^2\sin^2\theta
$$
$$
L^2\dot\theta^2(\cos^2\theta+\sin^2\theta)
$$
$$
|\vec v_B|^2=L^2\dot\theta^2
$$

$$
T=\frac{1}2 mL^2\dot\theta^2
$$
**Potential Energy**
$$
U=-m(\vec g\cdot\vec r_{OB})
$$
$$=-m((-g\vec j)\cdot(L\sin(\theta)\vec i-L\cos(\theta)\vec j)
$$
$$
U=-mgL\cos\theta
$$
![[Principles_of_Physical_Modelling/images/Pasted-image-20231011092309.png|400]]

**Lagrangian**
$$
L=T-U
$$
$$
L=\frac{1}2 mL^2\dot\theta^2+mgL\cos\theta
$$
**Equation of motion**
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial\dot\theta}\right)-\frac{\partial L}{\partial \theta}=0
$$
$$
\Rightarrow \frac{d}{dt}(mL^2\dot\theta)-(-mgL\sin\theta)=0
$$
$$
\Rightarrow mL^2\ddot\theta+mgL\sin\theta=0
$$
$$
\Rightarrow\ddot\theta+\frac{g}L\sin\theta=0
$$
Note: When the degree $\theta$ is small enough, then $\sin\theta=\theta$

**Equilibrium**
$$
\frac{\partial L}{\partial \theta}=0
$$
$$
\Rightarrow -mgL\sin\theta=0
$$
$$
\sin\theta=0
$$
$$
\Rightarrow\theta=0\approx\pi
$$

**Stability**
$$
K=-\frac{\partial^2L}{\partial\theta^2}=-\frac{\partial}{\partial\theta}(-mgL\sin\theta)
$$
$$
=mgL\cos\theta
$$
When $k\ge0$, it is stable. 
When $k<0$, it is unstable
____
## Example
We have a ball at point $A$ which is on a hemisphere, and $A$ is attached to a ball $B$. $A$ is rolling on the hemisphere, and $B$ is just freely following $A$. 

Ball $A$ has mass $m_1$ and Ball $B$ has mass $m_2$

![[Principles_of_Physical_Modelling/images/Pasted-image-20231011093956.png|400]]
### Solution
In this example, the ball $B$ acts like a pendulum.

**Kinetic Energy**
Velocity of $A$
$$
\vec v_{A}=\vec V_0+\vec\omega_1\times\vec r_{OA},\,\,\,\, \vec\omega_1=\dot\phi\vec k
$$
$$
=\dot\phi\vec k\times(R\sin\phi\vec i0R\cos\phi\vec j)
$$
$$
=R\dot\phi\cos\phi\vec i_R\dot\phi\sin\phi\vec j
$$
$$
|\vec v_A|^2=R^2\dot\phi^2
$$
Velocity of $B$
$$
\vec v_B=\vec v_A+\omega_2\times\vec r_{AB}
$$
$$
=R\dot\phi\cos\phi\vec i+R\dot\phi\sin\phi\vec j+\dot\beta\vec k\times(L\sin\beta\vec i-L\cos\beta\vec j)
$$
$$
=R\dot\phi\cos\phi\vec i+R\dot\phi\sin\phi\vec j+\beta L\sin\beta\vec j+\dot\beta L\cos\beta\vec i
$$
$$\vec v_B=(R\dot\phi\cos\phi+\dot\beta L\cos\beta)\vec i+(R\dot\phi\sin\phi+\dot\beta L\sin\beta)\vec j
$$
$$
|\vec v_B|^2=R^2\dot\phi^2\cos^2\phi+\dot\beta^2L^2\cos^2\beta+2R\dot\phi\dot\beta L\cos\phi\cos\beta+R^2\dot\phi^2\sin^2\phi+\dot\beta L^2\sin^2\beta+2R\dot\phi\dot\beta L\sin\phi\sin\beta
$$
$$
=R^2\dot\phi^2\dot\beta^2L^2+2R\dot\phi\dot\beta L\cos(\phi-\beta)
$$

Bringing the above velocities together
$$
T=\frac{1}2 m_1|\vec v_A|^2+\frac{1}2 m_2|\vec v_B|^2
$$
$$=\frac{1}2 R^2\dot\phi^2m_1+\frac 1 2 m_2(R^2\dot\phi^2+\dot\beta^2L^2+2R\dot\phi\dot\beta L\cos(\phi-\beta))
$$
**Potential Energy**
$$
U=-m_1(\vec g\cdot\vec r_{OA})-m_2(\vec g\cdot \vec r_{OB})
$$
$$
=-m_1gR\cos\phi-m_2((-g\vec j)\cdot(R\sin\phi\vec i-R\cos\phi\vec j+L\sin\beta\vec i-L\cos\beta\vec j))
$$
$$
U=-m_1gR\cos\phi-m_2g(R\cos\phi+L\cos\beta)+\text{ constant}
$$
**Lagrangian**
$$
L=T-U
$$
$$
=\frac 12 R^2\dot\phi^2m_1+\frac 12 m_2(R^2\dot\phi^2+\dot\beta^2L^2+2R\dot\phi\dot\beta L\cos(\theta-\beta)) +m_1gR\cos\theta+m_2g(R\cos\phi+L\cos\beta)
$$
**Equations of Motion**
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial\dot\phi}\right)-\frac{\partial L}{\partial \phi}=0
$$
$$
\Rightarrow\frac{d}{dt}(R^2\dot\phi m_1+m_2R^2\dot\phi+2R\dot\beta L\cos(\phi-\beta))-(-m_2R\dot\phi\dot\beta L\sin(\phi-\beta)-m_2gR\sin\phi)=0
$$
$$
\Rightarrow \begin{align*} &m_1R^2\ddot\phi+m_2R^2\ddot\phi+2R\ddot\beta L\cos(\phi-\beta)\\ &-2R\dot\beta L\sin(\phi-\beta)(\dot\phi-\dot\beta)+m_2R\dot\phi\dot\beta L\sin(\phi-\beta)\\ &+m_2gR\sin\phi\end{align*} = 0
$$
Calculating the second equation of motion
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot\beta}\right)-\frac{\partial L}{\partial\beta}=0
$$
$$
\Rightarrow(m_1R^2+m_2R^2)\ddot\phi+m_2R\ddot\beta L\cos(\phi-\beta)+R(\dot\beta)^2L\sin(\phi-\beta)m_2+m_2gR\sin\phi=0
$$
$$
m_2L^2\ddot\beta+m_2RL\ddot\phi(\cos(\phi-\beta)-\ddot\phi^2\sin(\phi-\beta))+m_2gL\sin\beta=0
$$

**Equilibrium**
Calculating the partial differentiation of L with respect to $\beta$
$$
\frac{\partial L}{\partial \beta}=0
$$
$$
\Rightarrow m_2gL\sin\beta=0
$$
$$
\Rightarrow\beta_1=0\text{ or }\pi=\beta_2
$$
Calculating the partial differentiation of L with respect to $\phi$
$$
\frac{\partial L}{\partial \phi}=0
$$
$$
\Rightarrow gR(m_2+m_1)\sin\phi=0
$$
$$
\Rightarrow \phi_1=0\text{ or }\phi_2=\pi
$$
$$
(0,0),\, (0,\pi),\, (\pi,0),\, (\pi,\pi)
$$
**Stability**
*Mass Matrix M*
$$
\frac{\partial^2L}{\partial\dot\beta^2}\Bigg|_{\phi=\dot\beta=0}=\frac{\partial}{\partial \dot\beta}(m_2L^2\dot\beta+m_2RL\dot\phi\cos(\phi-\beta))=m_{11}=m_2L^2
$$
$$
M_{12}=\frac{\partial^2L}{\partial \dot\beta\partial\dot\phi}=\frac{\partial}{\partial\dot\beta}(m_2R^2\dot\phi+m_2R^2\dot\phi+m_2RL\beta\cos(\phi-\beta))
$$
$$
=m_2RL\cos(\phi-\beta)
$$
$$
M=\begin{bmatrix}m_2L^2& m_2RL\cos(\phi-\beta)\\ m_2RL\cos(\phi-\beta)& R^2(m_1+m_2)\end{bmatrix}
$$
**Stiffness Matrix**
$$
K_{11}=-\frac{\partial^2L}{\partial \beta^2}\Bigg|_{\dot\phi=\dot\beta=0}=-\frac{\partial}{\partial\beta}(m_2RL\dot\phi\dot\beta\sin(\phi-\beta)-m_2gL\sin(\beta))
$$
$$
=m_2gL\cos\beta
$$
$$
K=\begin{bmatrix}m_2gL\cos\beta & 0 \\ 0 & gR(m_1+m_2)\cos\phi\end{bmatrix}
$$
$(0,0)$
$$
M=\begin{bmatrix}m_2L^2& m_2RL\\ m_2RL& R^2(m_1+m_2)\end{bmatrix},\,\, K=\begin{bmatrix}m_2gL& 0\\ 0&gR(m_1+m_2)\end{bmatrix}
$$
$$
m_1=m_2=1kg,\,\, R=L=1m,\,\, g=10\, ms^{-2}
$$
$$
M=\begin{bmatrix}1&1\\1&2\end{bmatrix},\,\,\, K=\begin{bmatrix}10&0\\0&20\end{bmatrix}
$$
$$
\text{det}\begin{pmatrix}10-\omega^2&-\omega^2\\-\omega^2&20-2\omega^2\end{pmatrix}=\text{det}(K-\omega^2M)=0
$$
$$
(10-\omega^2)(20-2\omega^2)-\omega^4=0
$$
$$2\omega^4-40\omega^2+200-\omega^4=0
$$
$$
y^2-40y+200=0
$$
$$
y=\omega^2=5.68\text{ or }34.14
$$
$$
\omega_1=2.42\, s^{-1}
$$
