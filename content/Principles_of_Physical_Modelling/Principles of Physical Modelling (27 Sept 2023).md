---
title: Lecture 1
draft: false
date: 27 Sept 2023
---


- This course is a bridge between Engineering Science and Continuum Mathematics.
- Cumulative Exam in January (3 hours)
- Experimental kit will be given that relates to the concepts taught in class. A short video has to be produced on your findings.

# The modelling process
There are five steps in the modelling process:
1. Problem identification
2. Model formulation
	- **Discrete models:** Typically write down equations of motion for individual elements and their couplings
		- Examples: mass-spring systems, agent-based models
	- **Kinetic/statistical/ML models:** These models are used when you have an abundance of data, and can be used to make predictions based on the past.
		- Examples: Weather forecasting, predicting kinetic models
	- **Continuum models:** Models are described in partial differential equations, to describe models in bulk. 
		- Example: Modelling waves, wind
3. Analysis + Computation
	- We try to look at a simplified version of a model to gain some intuition to solve the complex problem
	- We analyze the model using techniques using partial differential equations or dynamical systems or some other method.
	- We also try to see if the problem is amenable to a computational or numerical method
4. Compare predictions against data + model validation
	- Your model is only as good as the predictions it makes. Thus, you have to test your model against new data and validate it against your theoretical values.
5. Return back to Step 2, and continue until you converge on a satisfactory solution

# Units
- The physical parameters will have units expressed in terms of 7 fundamental quantities:
	- Mass (kilograms)
	- Length (meters)
	- Time (seconds)
	- Temperature (Kelvin)
	- Current (Ampere)
	- Amount of substance (mol)
	- Intensity (Candela (cd))
- You can combine the above fundamental quantities to get new quantities:
	- Velocity in $ms^{-1}$
	- Force 
	- $\dots$

# Dimensional consistency
- Any equation modelling a physical process must be dimensionally consistent
- Every term in your equation of interest has to be consistent dimensionally.
	- This check is the most basic test that you can do in your modelling process.
Is the following dimensionally consistent?
$$
v=u+at^2
$$
where $v,u:\text{ velocity}, \, a:\text{ acceleration},\, t:\text{ time}$

Describing the above equation in dimensions would be

$$
[L][T]^{-1} =[L][T]^{-1}+[L][T]^{-2}[T]^2
$$

$$
[L][T]^{-1} =[L][T]^{-1}+[L]\cancel{[T]^{-2}}\cancel{[T]^2}
$$

So, its not dimensionally consistent

Example: What are the dimensions of $\omega$?
$$
\frac{d^2x}{dt^2}+\omega^2x=0
$$
The above formula is a Simple Harmonic motion
Describing the above equation in dimensions would be
$$
[L][T]^{-2}+[\omega^2][L]
$$
So $\omega$ must have dimensions $[T]^2$ 

# Dimensional Analysis
We can learn a lot from considering the physical mechanics at play and assessing their relative importance through the formation of dimensionless groups

Consider deriving an expression for the time period of a simple pendulum
The period has dimension $[T]$
Units that are given are length of the pendulum $l$, mass of the pendulum $m$ and gravitational constant $g$

$m \backsim [M]$, we can cancel out mass as its not wanted in the final dimension of the time period.
$l\backsim [L]$
$g\backsim [L][T]^{-2}$
So, the period $P$ is 
$$
P\backsim \sqrt{\frac l g}
$$
Thus, 
$$
P=k\sqrt{\frac l g}
$$
Experiment: 
$l=l_0$
$\Rightarrow P_0=k\sqrt{\frac {l_{0}}g},\,\, k=\frac{P_0}{\sqrt{\frac{l_0}g}}$

$$
P=\cfrac{P_0}{\sqrt{\frac{l_{0}}g}}\sqrt{\frac{l}g}
$$

Lets take a differential equation of simple harmonic motion
$$
\frac{d^2\theta}{dt^{2}}+\frac{g}{l}\theta=0
$$
$$
\theta=a\cos\left(\sqrt{\frac g l} t\right)+b\sin\left(\sqrt{\frac g l}t\right)
$$
$$
P=2\pi\sqrt{\frac l g}
$$
### Taylor Blast problem 
G.I. Taylor was asked to predict the amount of energy would be released by a nuclear blast. How to make a prediction, even though much of the information was classified?

The initial shockwave would have a radius of $r$ in time $t$, and the density $\rho$, with an energy of $E$
$$
r\backsim \rho^{\alpha}E^{\beta}t^\gamma
$$
The dimensions of the above equation would be
$$
[M]^0[T]^0[L]^1\backsim [M]^{\alpha}[L]^{-3\alpha}[M]^\beta[L]^{2\beta}[T]^{-2\beta}[T]^\gamma
$$
$$
-3\alpha+2\beta=1
$$
$$
\begin{align}\alpha+\beta&=0\\ -2\beta+\gamma&=0 \end{align}
$$
After calculations, 
$$
r=C\rho^\frac{-1}{ 5}E^\frac{1}{5}t^\frac{2}{5}
$$
$$
E=\frac{C_{*}r^5\rho}{t^2}
$$
After verifying with images of the Trinity Test by the Americans, $$E\backsim 4\times 10^{13}J\backsim 10 \text{ kilotonnes of TNT}$$
# Non-dimensionalization

Lets take an equation where $u$ and $U$ are speeds such that
$$
u=U\hat u
$$
In this case, $\hat u$ has no dimensions because 
$$
\hat u=\frac{u}U=1
$$
### Fluid flow and advection-diffusion problem
Governing equation
$$
\rho c\left(\frac{\partial T}{\partial t}+\hat u\cdot\nabla T\right)=k\Delta T
$$
Let $x, r=R(\hat x, \hat r), \, u=U\hat u$
$$
\rho c\left(\frac{\partial T}{\partial t} +\frac{u}{R}\hat u\cdot \hat\nabla T\right)=\frac{k}{R^{2}}\Delta T
$$
$$
t=\frac{R}{u} \hat t
$$
$$
\frac{\rho c U R}{k}\left(\frac{\partial T}{\partial t}+\hat u\cdot \hat\nabla T\right)=\Delta T
$$
$$
T=T_\infty + (t_0-T_{\infty})\hat T
$$
Boundary Conditions
$$
\begin{gather}\hat T\rightarrow 0 \text{ as }r\rightarrow\infty \\ \hat T=1 \text{ on }r=R\end{gather}
$$