---
title: Lecture 1
date: 23 Jan 2024
---
# Introduction to Partial Differential Equations (PDEs)
We know about ordinary differential equations (ODEs), and how to solve them
Example of an ODE:
$$
m\frac{d^2u}{dt^2}+c\frac{du}{dt}+ku=f(t)
$$
The solution $u$ is a function of one independent variable 

But, in PDEs, we have **more than one independent variable**.
Example of a PDE:
$$
\mu\frac{\partial^2 u}{\partial t^2}+\frac{\partial^2}{\partial x^2}\left(El\frac{\partial^2 u}{\partial x^2}\right)=f(x,t)
$$

## When will we encounter PDEs?
There are three great equations that come 
1. Heat equation
2. Wave equation
3. Laplace Equation

### Heat Equation
Model the diffusion of heat through a one-dimensional medium, with conduction coefficient $\alpha^2$
$$
\frac{\partial u}{\partial t}=\alpha^2\frac{\partial ^2 u}{\partial x^2}
$$
Note: Something that is wrong with this equation is that heat has infinite speed which is not true.

### Wave Equation
Model the vibration amplitude of a taut on-dimensional string with tension $T$ and mass density $\rho$, 
$$
\frac{\partial ^2 u}{\partial t^2}=c^2\frac{\partial ^2 u}{\partial x^2}
$$
There are many applications for this equation in Electro-magnetic waves, Radio Frequency waves, Waves at a Sea etc.

### Laplace Equation
Model the steady-state temperature distribution in a conductive sheet
$$
\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2u}{\partial y^2}=0
$$
Many applications include fluid mechanics, electrostatics, analytical functions etc.

## Other Examples
**Cable Equation** governing the voltage (or current) in a transmission line
$$
\frac{\partial^2 u}{\partial x^2}=LC\frac{\partial^2 u}{\partial t^2}+(RC+LG)\frac{\partial u}{\partial t}+RGu
$$
**Korteweg-de Vries (KdV) Equation** the governing amplitude $u(x,t)$ of dispersive waves
$$
\frac{\partial u}{\partial t}=\frac{\partial u}{\partial x}+\frac 3 2 u\frac{\partial u}{\partial x}+\frac{\partial^3 u}{\partial x^3}
$$
## Classifying PDEs
There are three things to consider
- The dependent variable (whatever is in the numerator)
- The independent variables (whatever is in the denominator)
- The order of a PDE (order of the highest derivate)

A *linear* PDE is one in which the dependent variables and their derivatives appear linearly in the equation
$$
\frac{\partial^2 u}{\partial x^2}+x\frac{\partial u}{\partial x}+y\frac{\partial u}{\partial y}=\sin(x)
$$

A *linear homogenous* PDE is a linear PDE in which all terms contain a dependent variable or its derivate
$$
\frac{\partial^2 u}{\partial x^2}+x\frac{\partial u}{\partial x}+y\frac{\partial u}{\partial y}=0
$$

A *semilinear* PDE is one in which is linear if you only consider the terms in the equation with the highest derivatives
$$
\frac{\partial^3 u}{\partial x^3}+e^{4xy}\frac{\partial^3 u}{\partial x^2\partial y}+u\frac{\partial u}{\partial x}=\sin(x)
$$

A *nonlinear* PDE is one that is not linear or semilinear.
$$
u\frac{\partial^2u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}+u^2=0
$$
**Example:**
$$
\frac{\partial^2 u}{\partial x^2}+x\frac{\partial u}{\partial x}+y\frac{\partial u}{\partial y}=\sin(x)
$$
has dependent variables $u$, independent variables $x,y$ and order 2.

### Linearity
There are two criteria for linearity.

So lets take a function $f:R\rightarrow R$

The first criteria is 
$$
f(x+y)=f(x)+f(y)\,\,\,\,\,\,\,\,x,y\in R^n\,\,\, x\ne y
$$
The second criteria is 
$$
f(\lambda x)=\lambda f(x)\,\,\,\,\,\, \lambda \in R
$$

## Worked Example 4.1
1)
$$
\left(\frac{\partial u}{\partial x}\right)^2+\frac{\partial u}{\partial y}+3u=0
$$
$$
\begin{array}{c|c|c|c}\text{dependent variable}&\text{independent variable}&\text{order}&\text{type}\\\hline u&x,y&1&\text{nonlinear}\end{array}
$$
2)
$$
r\theta^2\frac{\partial^2 V}{\partial r^2}+\sin\theta\frac{\partial ^2V}{\partial^2\theta}+(r^2-\theta^2)\frac{\partial^2V}{\partial\theta\partial r}=0
$$
$$
\begin{array}{c|c|c|c}\text{dependent variable}&\text{independent variable}&\text{order}&\text{type}\\\hline V&r,\theta &2&\text{linear homogenous}\end{array}
$$

3)
$$
\frac{\partial^2 x}{\partial t}+\frac{\partial^2 x}{\partial s^2}+\sin x=0
$$
$$
\begin{array}{c|c|c|c}\text{dependent variable}&\text{independent variable}&\text{order}&\text{type}\\\hline x&s,t&2&\text{semilinear}\end{array}
$$
4)
$$
y^2\frac{\partial^2u}{\partial x^2}+\frac{\partial u}{\partial y}+\sin x=0
$$
$$
\begin{array}{c|c|c|c}\text{dependent variable}&\text{independent variable}&\text{order}&\text{type}\\\hline u&x,y&2&\text{linear inhomogenous}\end{array}
$$
5)
$$
\mu \frac{\partial u}{\partial t^2}+\frac{\partial^2}{\partial x^2}\left(EI(x)\frac{\partial^2 u}{\partial x^2}\right)=f(x,t)
$$
$$
\begin{array}{c|c|c|c}\text{dependent variable}&\text{independent variable}&\text{order}&\text{type}\\\hline u&x,t&4&\text{linear inhomogenous}\end{array}
$$
6)
$$
\frac{\partial \phi}{\partial t}+\frac{\partial^3\phi}{\partial x^3}-6\phi\frac{\partial \phi}{\partial x}=0
$$
$$
\begin{array}{c|c|c|c}\text{dependent variable}&\text{independent variable}&\text{order}&\text{type}\\\hline \phi&t,x&3&\text{semilinear homogenous}\end{array}
$$
