---
title: Lecture 6
date: 08 Nov 2023
---
### Recap
Suppose you have a region indicated by the square in the image, and you have two types of species (A and B), and you have a bunch of each type. This region is part of a larger region, where its encapsulated by millions of these species. So, we take a zoomed out approach to modelling the system. 
![[Principles_of_Physical_Modelling/images/Pasted-image-20231108091418.png|500]]
When A and B react with each other, they give out C
$$
A+B\rightarrow C
$$
So the rate of change for A and B
$$
\frac{dA}{dt}=\frac{dB}{dt}=-r
$$
And the rate of change of C
$$
\frac{dC}{dt}=r
$$
By the **Law of Mass Action** (an assumption!!)
$$
\huge\boxed{r=kA^\alpha B^\beta}
$$
So,
$$
\alpha A+\beta B\rightarrow\gamma C+\delta D
$$
The kinetic equations would be
$$
\frac{dA}{dt}=-\alpha k\, A^\alpha B^\beta
$$
Note: the negative symbol is there because you are losing A as time goes on. The opposite applies for C.
$$
\frac{dC}{dt}=\gamma\, k\, A^\alpha\, B^\beta
$$
____
## Example: SIR Model
This model is an epidemic model, and it tells the number of people susceptible to the disease (S), the number of infected people (I), and the number of recovered people (R). 

If a susceptible person to the disease meets an infected person, then they both become infected. 
$$
S+I\rightarrow 2I \tag{1}
$$
If the disease doesn't kill a person, and if the infected person recovers
$$
I\rightarrow R \tag{2}
$$

Rate of S is
$$r_1=k_1 SI
$$
The kinetic equation of S is
$$
\boxed{\frac{dS}{dt}=-r_1=-k_1SI}
$$
Rate $r_2$ is
$$
r_2=k_2I
$$
Kinetic equation of R is 
$$
\boxed{\frac{dR}{dt}=k_2I}
$$
Kinetic equation of I is
$$
\frac{dI}{dt}=-k_1SI+2k_1SI-k_2I
$$
$$
\boxed{\frac{dI}{dt}=-k_2I+k_1SI}
$$
These 3 ODE's comprise the SIR model.

**Concept**: Conserved quantities: $\frac{d}{dt}(\dots)=0$ 
So,
$$
\frac d{dt}(S+I+R)=0
$$
This equation is a statement that tells us the total population $N$ remains fixed over time (no births and no deaths).

**Concept**: Steady-states
$$
\frac{dS}{dt}=\frac{dI}{dt}=\frac{dR}{dt}=0
$$
It tells us that the rates of change of each term is zero.
____
## The Lotka-Volterra Model or a "predator-prey" system
$$
\frac{dR}{dt}=aR-bRW
$$
$$
\frac{dW}{dt}=-cW+dRW
$$
R represents the number of rabbits, and W represents the number of wolves (eats rabbits). This model tells us that the rabbits are eaten by the wolves, but if there are no rabbits then the wolves die out.

Need 
$$
\boxed{\alpha R\rightarrow \beta R} \tag{1}
$$
$$
\frac{dR}{dt}=-\alpha k_1 R^\alpha +\beta k_1 R^\alpha
$$
$$
=k_1(\beta-\alpha)R^\alpha
$$
$$
\rightsquigarrow \alpha=1,\,\,\,\, k_1(\beta-1)=\alpha
$$
$$
\boxed{\alpha R+\beta W\rightarrow rW},\,\,\, r_2=k_2R^\alpha\, W^\beta \tag{2}
$$
$$
\frac{dR}{dt}=-\alpha\, k_2R^\alpha W^\beta,\,\,\,\, \frac{dW}{dt}=-\beta\, k_2\,R^\alpha\, W^\beta+\gamma k_2\, R^\alpha\, W^\beta
$$
From eq (2)
$$
\alpha=\beta=1,\,\,\,\,\,\,\,\,\,\,\, k_2=b
$$
$$
k_2(\gamma-1)=d
$$
So,
$$
R\rightarrow 2R
$$
$$
R+W\rightarrow 2W
$$
We have a decrease in number of wolves as the number of rabbits decrease. 
And the wolves go to deceased wolves
$$
W\rightarrow DW
$$
Note: you should be very critical of this model, as there are many uncertainties in this model. 
____
## Michaelis-Menten Model
Imagine you have a blob S, and you have an enzyme E. The enzyme combines with S and form an intermediate blob called C, and the enzyme detaches and you are left with a blob P. 
![[Principles_of_Physical_Modelling/images/Pasted-image-20231108101153.png|400]]

The equations are:
$$
S+E\leftrightharpoons C
$$
$$
C\rightarrow P+E
$$
The kinetic equations are
$$
\frac{dS}{dt}=-k_1SE+k_2C
$$
$$
\frac{dE}{dt}=-k_1SE+k_2C+k_3C
$$
$$
\frac{dC}{dt}=k_1SE-k_2C-k_3C
$$
$$
\frac{dP}{dt}=k_3C
$$
$$
S(0)=S_0,\,\,\, E(0)=E_0,\,\, \underbrace{C(0)}_{C_0}=\underbrace{P(0)}_{P_0}=0
$$
So,
$$
\frac{d}{dt}(E+C)=0
$$
$$
\frac{d}{dt}(S+C+P)=0,\,\,\,\,\,\,\, S(t)+C(t)+P(t)=\text{const}
$$
$$
\rightsquigarrow S+C+P=S_0 \rightsquigarrow P=P(C, S)
$$
$$
\huge\boxed{\begin{align*}\frac{dS}{dt}&=-k_1 E_0S+(k_1S+k_2)C\\[0.5em] \frac{dC}{dt}&=k_1E_0S-(k_1S+k_2+k_3)C\end{align*}}
$$
The Steady states are
$$
S=C=0\,\,\,\,\,\,\,\,\,\,\text{as }t\rightarrow\infty
$$
$$
E=E_0
$$
**Non-dimensionalize**
$$
S=S_0s,\,\,\,\,\,\, E=E_0e,\,\,\,\,\, C=E_0c
$$
where $[S/E/C]=\text{mol or M}$
$$
t=t_0\tau=\frac{1}{k_1E_0}\tau
$$
For example:
$$
\frac{dS}{dt}=S_0\frac{d}{dt}s(\tau)
$$
$$
=S_0\frac{ds}{d\tau}\frac{d\tau}{dt}=S_0\,E_0\,k_1\frac{ds}{d\tau}
$$

**Check:**
$$
\frac{ds}{d\tau}=-s+(s+\mu)c,\,\,\,\,\,\,\,\, s(0)=1
$$
$$
\epsilon\frac{dc}{d\tau}=s-(s+k)c,\,\,\,\,\,\,\, C(0)=0
$$
$$
\mu=\frac{k_2}{S_0\, k_1}
$$
$$
k=\frac{k_2+k_3}{S_0\, k_1}
$$
$$
\epsilon=\frac{E_0}{S_0}<< 1
$$
This tells us that we need a very low concentration of enzyme to kick off the reaction.
So,
$$
\rightsquigarrow\boxed{C\approx \frac{s}{s+k}}
$$
With Asymptotic analysis + singular perturbation 
$$
\tau=\epsilon T,\,\,\,\,\,\,\frac{dc}{d\tau}=\frac{1}\epsilon \frac{dC}{dT}
$$
