---
title: Lecture 1
date: 26 Sept 2023
---

# Introduction
- To do calculus in the real-world, we need to do calculus in 3D. 
- This course is to do techniques in vector calculus, which has important applications in Artificial Intelligence, Construction, and more.
## What is vector calculus?
**Vector Calculus** = calculus grown up
- Vector Calculus is a language to understand realistic engineering.

### Scalar Function
Functions that take a single input and produce a single output
Examples: $sin(x)$, $cos(x)$, height of something as it varies over time

### Vector Function
Takes a scalar as input, and returns a vector 
$$
v(t)=v_{1(t)i}+v_2(t)j+v_3(t)k = (v_1(t),v_2(t),v_3(t))
$$
Each of the inputs in the above function is a scalar, and it generates a vector function $v(t)$.

### Scalar Field $\phi$
Scalar field $\phi$ is a scalar quantity defined over a region of space. It takes a vector (of positions) and returns a scalar.
$$
\phi= f(x,y,z)=f(r)\,\,\,\, (\text{or }f(x,y) \text{ in 2D})
$$
Example: the variation of temperature $T(x,y,z)$ in a room using Cartesian co-ordinates. 

### Vector Field
A vector field $v(x,y,z)$ is a vector-valued quantity defined over a region of space. It is defined by a field that takes a vector (of positions) and returns a vector
$$
v(r)=v_{1(x,y,z)i}+ v_2(x,y,z)j+v_3(x,y,z)k
$$
Example: the spatial variation of fluid velocity $v(x,y,z)$ in a steady flow, or current $I(x,y,z)$ flowing in a conductor

## Vector Functions
Takes a scalar input (such as time), and returns a vector. Can we visualized as a stack of scalar functions.
Differentiation:
$$
\frac{d}{{dt}}v(t)= \frac{d}{{dt}} v_{1(t)}i+ \frac{d}{dt}v_2j+\frac{d}{dt} v_{3}k
$$
**Worked Example 1.1**: A particle moves on a circle of radius 1, such that its position vector is given by 
$$
r(t)=\sin t\vec{i}+\cos t\vec{j}
$$

Calculate its velocity and acceleration. Show that the velocity and acceleration are orthogonal. Is 

$$
\left|{\frac{dr}{dt}}\right| = \frac{d}{dt}|\vec r|?
$$
**Solution:**
$r(t)=\sin (t)\vec i+\cos (t)\vec j$

$\vec v=\frac{d}{dt} r(t)= \cos(t)\vec i -\sin(t)\vec j$

$\vec a=\frac{d}{dt}v(t)=-\sin(t)\vec i-\cos(t)\vec j$ 
Show $\vec v\cdot \vec a = 0$

$=\begin{pmatrix}\cos(t) \\ -\sin(t)\end{pmatrix} \cdot \begin{pmatrix}-\sin(t)\\ -\cos(t)\end{pmatrix}=0$

The reason why $\left|{\frac{dr}{dt}}\right| = \frac{d}{dt}|\vec r|$ is not true is because the derivative of 1 is 0, whereas $\frac{dr}{dt}\not= 0$ 

### Rules of differentiations
The rules of differentiations are obtained by applying the rules to the separate components.
$$
(fg)'=f'g+g'f
$$
$$
(\vec u\cdot \vec v)'=\vec u'\cdot \vec v+\vec u\cdot \vec v'
$$
$$
(\vec u\times \vec v)'=\vec u'\times \vec v+\vec u\times \vec v'
$$
You can prove the above 2 rules by considering the product rule 

$$
(\vec u+\vec v)'=\vec u'+\vec v'
$$
$$
(c\vec u)'=c\vec u'
$$

An important type of vector function is the **intrinsic definitions of a curve** $r(t)$ in 3 dimensions
$$
r(t)=(x(t),y(t),z(t)) = x(t)\vec i +y(t)\vec j +z(t)\vec k
$$
Example:
- A straight line $\vec r=\vec a+t\vec b$
- circle $\vec r=(a\cos t, a\sin t,0)$ in the $(x,y)$ plane

Tangent vector to the curve:
$$
\vec r'(t)=(x'(t),y'(t),z'(t))=\left(\frac{dx}{dt},\frac{dy}{dt},\frac{dz}{dt}\right)
$$
If you were to change $t$ to $t^2$, it would essentially not change the curve nor the direction of the tangent vector. 


