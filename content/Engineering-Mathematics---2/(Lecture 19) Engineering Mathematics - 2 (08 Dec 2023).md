---
title: Lecture 19
date: 08 Dec 2023
---
### Worked Example 3.2
Use Laplace Transforms to show the solutions of the differential equation
$$
\frac{dx}{dt}+7x=e^{-4t},\,\,\,\,\,\,\, \text{ with }x(0)=2\tag{time domain system}
$$
The output is $x(t)$

**Step 1**: Take the LT of the ODE (both sides!!)
$$
L\left[\frac{dx}{dt}+7x\right]=L\left[e^{-4t}\right]
$$
Using linearity
$$
L\left[\frac{dx}{dt}\right]+7L[x]=L\left[e^{-4t}\right]
$$
Use the LT of a derivative and LT of known functions
$$
\overbrace{sX(s)-\underbrace{x(0)}_{2}}^{L\left[\frac{dx}{dt}\right]}+7X(s)=\frac{1}{s+4}
$$
Collect like terms 
$$
(s+7)X(s)-2=\frac{1}{s+4}\tag{Laplace domian}
$$
**Step 2:** Solve for $X(s)$
$$
(s+7)X(s)=2+\frac{1}{s+4}=\frac{2(s+4)+1}{s+4}=\frac{2s+9}{s+4}
$$
$$
\boxed{X(s)=\frac{2s+9}{(s+4)(s+7)}}
$$
**Step 3:** Reduce $X(s)$ to known transforms
Here, we can use partial fractions
$$
\frac{2s+9}{(s+4)(s+7)}=\frac{A}{s+4}+\frac{B}{s+7}
$$
(recall that $L[e^{-at}]=\frac{1}{s+a}$)
Partial fractions:
$$
A=\frac{1}{3},\,\,\,\,\,\,\, B=\frac 5 3
$$
So,
$$
X(s)=\frac{1}{3}\cdot\frac{1}{3+4}+\frac{5}{3}\cdot \frac{1}{s+7}
$$
$$
=\frac{1}{3}L\left[e^{-4t}\right]+\frac{5}3 L\left[e^{-7t}\right]
$$
$$
X(s)=L\left[\frac{1}3 e^{-4t}+\frac 5 3 e^{-7t}\right]
$$
**Step 4:** Take the inverse Laplace transforms $L^{-1}$
$$
x(t)=\frac{1}3 e^{-4t}+\frac{5}3 e^{-7t}
$$
## Properties of LT: the shifting theorems
The first shifting theorem: A shift in s corresponds to multiplication by an exponential in t
$$
L\left[e^{-at}f(t)\right]=F(s+a)
$$
The second shifting theorem: A shift in t corresponds to multiplication by an exponential in s
$$
L\left[H(t-a)f(t-a)\right]=e^{-as}F(s)
$$

### Worked Example 3.3
##### **Part 1**

$$
\frac{d^2x}{dt^2}+6\frac{dx}{dt}+9x=0,\,\,\,\,\,\, x(0)=2,\,\,\frac{dx}{dt}(0)=10\tag{time domain}
$$
Find the output $x(t)$ using Laplace Transforms

**Step 1** Take the LT of the ODE
$$
L\left[\frac{d^2x}{dt^2}+6\frac{dx}{dt}+9x\right]=L[0]
$$
Use Linearity
$$
L\left[\frac{d^2x}{dt^2}\right]+6L\left[\frac{dx}{dt}\right]+9L[x]=0
$$
LT of the derivatives 
$$
\overbrace{s^2X(s)-sx(0)-\frac{dx}{dt}}^{L\left[\frac{d^2x}{dt}\right]}+6(sX(s)-x(0))+9X(s)=0
$$
Plugging in known values, and collecting like terms
$$
\overbrace{(s^2+6s+9)}_{\text{the characteristic polynomial of the ODE!}}X(s)-2s-22=0\tag{s-domain}
$$
**Step 2:** Solve for $X(s)$
$$
(s^2+6s+9)X(s)=2s+22
$$
$$
X(s)=\frac{2s+22}{s^2+6s+9}
$$
**Step 3:** Rewrite $X(s)$ in terms of known LTs

Aim: factorize the polynomial on the bottom

root are $s=\frac{-6\pm\sqrt{36-4\cdot1\cdot 9}}{2}$
$$
s=-3\tag{repeated}
$$
$$
X(s)=\frac{2s+22}{(s+3)^2}
$$
Recall that $L[1]=\frac{1}s,\,\,\,\,\, L[t]=\frac{1}{s^2}$
We have a s-shifted version of these,

Rewrite in terms of $s+3$
$$
X(s)=\frac{2(s+3)+16}{(s+3)^2}
$$
$$
=2\cdot\frac{1}{s+3}+16\cdot \frac{1}{(s+3)^2}
$$
$$
=2L\left[1\cdot e^{-3t}\right]+16L\left[t\cdot e^{-3t}\right]
$$
These two equations on the top come from Standard LTs + 1st shifting theorem.
$$
X(s)=L\left[2e^{-3t}+16te^{-3t}\right]
$$
**Step 4:** Take inverse LT, $L^{-1}$
$$
\boxed{x(t)=2e^{-3t}+16te^{-3t}}
$$
##### Part 2
$$
\frac{d^2x}{dt^2}+4\frac{dx}{dt}+13x=0
$$
**Step 1**: Take LT of the ODE
$$
L\left[\frac{d^2x}{dt^2}+4\frac{dx}{dt}+13x\right]=L[0]
$$
Use Linearity and the LT of the derivative, plug in the initial conditions
$$
(s^2+4s+13)X(s)=4s+20
$$
**Step 2:** Solve for $X(s)$
$$
X(s)=\frac{4s+20}{s^2+4s+13}
$$

**Step 3:** Reduce $X(s)$ to known LTs

Factorize the denominator
Roots are $s=\frac{-4\pm\sqrt{16-4\cdot1\cdot13}}{2}$
Roots are complex 

An alternative is instead of factorizing we *complete the square*
$$
s^2+4s+13=(s+a)^2+b
$$
$$
=(s+2)^2+9
$$
$$
=(s+2)^2+3^2
$$
$$
\implies X(s)=\frac{4s+20}{(s+2)^2+3^2}
$$
Recall that 
$$
L[\cos(3t)]=\frac{s}{s^2+3^2}
$$
$$
L[\sin(3t)]=\frac{3}{s^2+3^2}
$$
Rewrite in terms of $s+2$
$$
X(s)=\frac{4(s+2)+12}{(s+2)^2+3^2}
$$
$$
=4\cdot \left[\frac{s+2}{(s+2)^2+3^2}\right]+4\frac{3}{(s+2)^2+3^2}
$$
$$
=4\cdot L\left[e^{-2t}\cos(3t)\right]+4L\left[e^{-2t}\sin(3t)\right]
$$
**Step 4:** Use linearity + inverse LT
$$
\boxed{x(t)=4e^{-2t}\cos(3t)+4e^{-2t}\sin(3t)}
$$

