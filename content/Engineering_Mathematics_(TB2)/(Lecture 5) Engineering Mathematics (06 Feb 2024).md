---
title: Lecture 5
date: 06 Feb 2024
---
# D'Alembert's Method

The separation of variables methods is one way of fining solutions of the wave equation, and its well suited to the case where we have boundary conditions.

- If we have an infinite domain, and no boundary conditions, then you are stuck!

When we have infinite structures (such as ponds, water ways, etc.), the solution we are looking for is a travelling wave.
### Theorem
The function $u(x,t)$ is given by
$$
u(x,t)=f(x-ct)+g(x-ct)
$$
is a solution of the wave equation for any function $f$ and $g$. IT is made up of two travelling waves with:
- fixed shape $f$, moving to the right at speed $c$
- fixed shape $g$, moving to the left, at speed $c$
___
Lets think about travelling waves
$$
u(x,t)=f(x-ct)+g(x+ct)
$$
When you have a travelling wave travelling to the right with a speed $c$ 

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240207111023.png|500]]

Lets say you have a wave travelling to the left with speed $c$, it hits the boundary (axis) and reflects to the right. This can be modelled using the D'Alembert method. 

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240207111204.png|500]]

## Example 6.1
Solve the wave equations 
$$
u_{tt}=c^2u_{xx},\,\,\,\,\,\,\, x\in R,\,\, t\ge 0
$$
The initial conditions are 
$$
\begin{array}{c}u(x,0)=0\\ u_t(x,0)=xe^{-x^2}\end{array}
$$

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240207111527.png|500]]

**Step 1**
Assume the d'Alembert Solution
$$
u(x,t)=f(x-ct)+g(x+xt)
$$
**Step 2**
Use initial conditions to find $f$, and $g$

At $t=0$
$$
u(x,0)=f(x)+g(x)\,\,\,\,\,\,\,\forall x\in R
$$
$$
\boxed{f(x)=-g(x)}
$$
The other initial condition
$$
\begin{split}u_t(x,t)&=\frac{\partial}{\partial t}\left[f(x-ct)+g(x+ct)\right]\\ &=f'(x-ct)(-c)+g'(x+ct)\cdot c\\ u_t(x,0)&=-cf'(x)+cg'(x)\\ &=cg'(x)+cg'(x)=2cg'(x)\\&=xe^{-x^2}\,\,\,\,\,\forall x\in R \end{split}
$$
Integrating both sides of the equations
$$
\int cg'(x)dx=\int xe^{-x^2}dx
$$
N.B: $\frac{d}{dx}e^{-x^2}=-2xe^{-x^2}$

$$
2cg(x)=-\frac{1}2 e^{-x^2}+k
$$
Then we figure out what $g(x)$ is
$$
g(x)=\frac{1}{2c}\left(-\frac{1}2 e^{-x^2}\right)+\frac{k}{2c}
$$
$$
f(x)=-g(x)=\frac{1}{4c}e^{-x^2}-\frac{k}{2c}
$$
So we have two functions, and we can plot them

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240207112643.png|500]]

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240207112720.png|500]]

**Step 4**
Putting it all together
$$
\begin{split}u(x,t)&=f(x-ct)+g(x+ct)\\ &=\frac{1}{4c}e^{-(x-ct)^2}-\frac{k}{2c}-\frac{1}{4c}e^{-(x+ct)^2}+\frac{k}{2c}\\ &=\frac{1}{4c}e^{-(x-ct)^2}-\frac{1}{4c}e^{-(x+ct)^2} \end{split}
$$
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240207112929.png|500]]

$$
u(x,t)=\frac{1}{4c}\left(e^{-(x-ct)^2}+e^{-(x+ct)^2}\right)\,\,\,\,\, \forall x\in R\,\,\,\,\,\,\, t\ge 0
$$
___
### Question: Why do we have travelling wave solutions?
All hyperbolic functions have
$$
Au_{xx}+Bu_{xy}+Cu_{yy}=f(u_x,u_y,u,x,y)
$$
$$
B^2-4AC>0\Rightarrow \text{ hyperbolic}
$$
$$
C(x,y),\,\,\,\eta(x,y)\Rightarrow \text{no clue how to solve}
$$
$$
u(x,y)=W(C(x,y),\eta(x,y))
$$
$$
\boxed{W_{C\eta}=h(W_C,W_\eta,W,C,\eta)}
$$
For the wave equation,
$$
C=x-ct,\,\,\,\eta=x+ct,\,\,\,\,\,\,\, W_{C\eta}=0
$$
___
$$
u(x,t)=W(x-ct, x+ct)
$$
$$
u_{xx}=W_{CC}+2W_{C\eta}+W_{\eta\eta}
$$
$$
u_{tt}=C^2(W_{CC}-2W_{C\eta}+W_{\eta\eta})
$$
The wave equation was 
$$
u_{tt}-c^2u_{xx}=0
$$
$$
-4c^2W_{C\eta}=0\Rightarrow W(C,\eta)=f(C)+g(\eta)
$$
This is the d'Alembert Solution




