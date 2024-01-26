---
title: Lecture 1
date: 26 Jan 2024
---
- 2-4 videos released a week ahead of the lecture, and must be watched before coming to the lecture.
- Each video will have a short homework or practice question.
- Submissions for the assessment worksheets are at 11:00 before the workshops on Tuesday.
___
Lets take a simple ordinary differential equation (ODE)
$$
\dot x=\sqrt{1-x^2}
$$
By a separation of variables
$$
\frac{dx}{\sqrt{1-x^2}}=dt\Rightarrow \arcsin x=t+c
$$
$$
x=\sin(t+c)
$$
When $c=0$
$$
x_1=\sin t\,\,\,\,\,\,\,\,\,\, \dot x_1=\cos t=\sqrt{1-\sin^2t}
$$
When $c=\frac{\pi}3$
$$
x_2=\sin\left(t+\frac{\pi}3\right)\,\,\,\,\,\,\,\,\,\,\,\, \dot x_2=\cos\left(t+\frac{\pi}3\right)=\sqrt{1-\sin^2\left(t+\frac{\pi}3\right)}
$$
$$
x_1+x_2=\sin t+\sin\left(t+\frac{\pi}3\right)
$$
$$
\frac{d}{dt}(x_1+x_2)=\sqrt{1-\sin^2 t}+\sqrt{1-\sin^2\left(t+\frac\pi 3\right)}
$$
$$
\ne \sqrt{1+\left[\sin t+\sin\left(t+\frac\pi 3\right)\right]^2}
$$
$$
=\sqrt{1-(x_1+x_2)^2}
$$

Lets take another ODE example,
$$
t^2\ddot x+10t\dot x+20x=0
$$
$$
x_1=t^{-4}\,\,\,\,\,\,\, x_2=t^{-5}
$$
are both solutions
$$
x=t^{-4}+t^{-5}
$$
$$
\dot x=-4t^{-5}-5t^{-6}\,\,\,\,\,\,\,\,\,\,\, \ddot x=20t^{-6}+30t^{-7}
$$
$$
t^2(20t^{-6}+30t^{-7})+10t(-4t^{-5}-5t^{-6})+20(t^{-4}+t^{-5})
$$
$$
t^{-4}(20-40+20)+t^{-5}(30-50+20)=0
$$
The second differential equation was linear, the first differential equation was non-linear, so we were able to use the superposition principle in the second differential equation (see Eng Maths 1).
	The linearity allowed us to find all the possible solutions for the second ODE.

##### Simple Pendulum
![[Applied_Linear_Algebra/images/Pasted_image_20240126122908.png|200]]

Using the Lagrangian and Eulerian formulas
$$
T=\frac 1 2 mL^2\dot\theta^2
$$
$$
U=-mgl\cos\theta
$$
$$
\ddot \theta=-\frac{g}l\sin\theta
$$
$$
\ddot\theta\approx -\frac{g}l\theta \tag{when theta is small}
$$
___
### Start with: Solutions
$$
Ax=b
$$
There are a particular set of linear equations where $b=0$, and these equations are called **Homogenous systems**.

In such cases, the Linear System can have
- One solution
- infinitely many solutions, or
- no solutions

In 3D,
When you have 3 planes on the x-axis, y-axis, and z-axis all intersect at one unique point. This means the linear system has **one solution** (as shown in the first image). 

When the three planes all intersect at a line, that means there are **infinitely many solutions** (as shown in second image).

When the three planes meet as parallel lines (looks like an infinite tent), this means the system has **no solutions** (as shown in third image).

![[Applied_Linear_Algebra/images/Pasted_image_px20240126123737.png]]

**Recap:**
$$
x+y+z=1
$$
$$
2x-y-2t=0
$$
$$
2x+y-3z=-6
$$
Writing the system of equations as a matrix
**note:** write this as line with equation TODO
$$
\left[\begin{array}{ccc|c}
1&1&1&1\\2&-1&-2&0\\2&1&3&-6\end{array}\right]
$$
$R_3\rightarrow R_3-R_2$
$R_2\rightarrow-2R_1$
$$
\left[\begin{array}{ccc|c}1&1&1&1\\0&-3&-4&-2\\0&2&-1&-6\end{array}\right]
$$
$R_3\rightarrow R_3+\frac{2}{3}R_2$
$$
\left[\begin{array}{ccc|c}1&1&1&1\\0&-3&-4&-2\\0&0&-\frac{4}3&-\frac{22}3\end{array}\right]
$$

This tells us that the Rank of A = 3
So it has one unique solution.

$$
-\frac{11}3z=-\frac{22}{3}
$$
$$
-11z=-22
$$
$$
\Rightarrow z=2
$$
$$
-3y-4z=-2
$$
$$
-3y-8=-2
$$
$$
-3y=6
$$
$$
\Rightarrow y=-2
$$
$$
x+y+z=1
$$
$$
x-2+2=1
$$
$$
\Rightarrow x=1
$$
___
Lets take another example of a set of equations
$$
2x-2y-2z=1
$$
$$
x+y+z=1
$$
The only possible solutions are either zero solutions or infinitely many solutions, which we can tell by looking at the pair of equations.
$$
\left[\begin{array}{ccc|c}2&-2&-2&1\\1&1&1&1\end{array}\right]
$$
$R_1\leftrightarrow R_2$
$$
\left[\begin{array}{ccc|c}1&1&1&1\\2&-2&-2&1\end{array}\right]
$$
$R_2\rightarrow R_2-2R_1$
$$
\left[\begin{array}{ccc|c}1&1&1&1\\ 0&-4&-4&-1\end{array}\right]
$$

So the Non-zero rows - 2
Number of unknowns - 3

The $\text{Rank }A=2<3$

The solutions
$$
z=t
$$
$$
-4y-4z=-1
$$
$$
-4y=-1+4z
$$
$$
-4y=-1+4t
$$
$$
y=\frac{1}4-t
$$
Solving for x
$$
x+\frac{1}4 -t+t=1
$$
$$
x=\frac{3}4
$$

