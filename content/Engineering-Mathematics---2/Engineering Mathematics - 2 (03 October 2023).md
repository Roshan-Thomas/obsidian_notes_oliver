---
title: Lecture 3
date: 03 Oct 2023
---

# Recap
Scalar function: Takes in a scalar and outputs a scalar

Vector function: Takes in a scalar and outputs a vector

Scalar field: Takes in a vector and outputs a scalar

Vector field: Takes in a vector and outputs a vector
____
# The gradient of a scalar field
One way to represent a scalar field, we can take a plane and put different colors to show different values of height. 

Another way is to draw concentric circles and along the circle the value of the heigh remains the same.

On a scalar field, we dont have a single value that shows the rate of change in a scalar field. The rate of change depends on the direction of the path taken (on the contour). 

Gradient Vector 
$$
\vec\nabla \phi=\text{grad }\phi =\frac{\partial \phi}{\partial x}\vec i+\frac{\partial\phi}{\partial y}\vec j+\frac{\partial \phi}{\partial z}\vec k=\left(\frac{\partial \phi}{\partial x},\frac{\partial\phi}{\partial y},\frac{\partial\phi}{\partial z}\right)
$$
Examples of scalar field
- Temperature and Pressure
	- A negative gradient will give us the direction of hot to cold
	- A positive gradient will give us the direction of cold to hot
	- And a gradient will tell us the direction of the temperature flow

A directional derivate $D_a$ of a scalar field tells us the direction of a gradient.
$$
D_a\phi(p)=\frac{d\phi(r(t))}{dt}\bigg\rvert_{t=0}
$$

**Example 2.1**
Calculate $\text{grad }\phi$ where 
$$
\phi=2xy+ax+z^2
$$
Evaluate at the origin and at the point $(a,a,a)$. Find the directional derivative in the direction $a=(1,1,1) at these 2 points.

**Solution:**
We have our scalar field $\phi(x,y,z)=2xy+ax+z^2$
$$
\text{grad }\phi=\vec\nabla\phi=\left(\frac{\partial\phi}{\partial x},\frac{\partial \phi}{\partial y},\frac{\partial \phi}{\partial z}\right)
$$
$$
=(2ya,2x,2z)
$$
$$
\vec\nabla\phi\vert_{x=0,\, y=0,\, z=0}=(a,0,0)
$$
$$
\vec\nabla\phi\vert_{x=a,\, y=a,\,z=a}=(3a, 2a, 2a)
$$
Directional Derivative 
$$
D_{\hat a}\phi=\hat a\cdot \vec\nabla \phi
$$
$$
\vec a=(1,1,1)
$$ 
So 
$$
\hat a=\frac{1}{\sqrt 3}(1,1,1)
$$
$$
\delta_{\hat a}\phi=\frac{1}{\sqrt 3} (1,1,1)\cdot(2y+a, 2x, 2z)
$$
$$
=\frac{1}{\sqrt 3}(2y+a+2x+2z)
$$
$$
=\frac{a+2(x+y+z)}{\sqrt 3}
$$
At $x=y=z=0$
$$
D_{\hat a}\phi=\frac{a}{\sqrt 3}
$$

$x=y=z=a$

$$
D_{\hat a}\phi=\frac{7a}{\sqrt 3}
$$

## Equation for the tangent plane to a surface
The equation of the tangent is defined as 
$$
(r-r_0)\cdot n=0,\Rightarrow (r-r_0)\cdot\nabla f|_{r=r_0}=0
$$
**Example 2.2**
Show that the equation for the tangent plane toa sphere, centre 0, of radius a, at a point $(x_0, y_0, z_0)$ is 
$$
xx_0+yy_0+zz_0=a^2
$$
When is the direction of the unit normal to the surface not defined?

**Solution**
Equation of a sphere is: 
$$
x^2+y^2+z^2=a^2
$$
We want to get a iso-sphere of the surface (a surface where all the values are the same)
Write in form $f(x,y,z)=\text{const}$

Our scalar field is going to be 
$$
f(x,y,z)=x^2+y^2+z^2
$$
because $a^2$ is constant

So, calculate normal to surface at a $r_0=(x_0,y_0,z_0)$
$$
\vec\nabla f|_{r_0}=\left(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},\frac{\partial f}{\partial z}\right)\bigg\vert_{r_0}=(2x,2y,2z)\vert_{r_0}
$$
$$
=2(x_0,y_0,z_0)
$$
Equation to the tangent plane at $r_0$ is 
$$
(r-r_0)\cdot\vec\nabla f|_{r_0}=0
$$
$$
\begin{pmatrix}x-x_0\\ y-y_0 \\ z-z_0\end{pmatrix}\cdot 2\begin{pmatrix}x_0\\y_0\\z_0\end{pmatrix}=0
$$
$$
xx_0-x_0^2+yy_0\cdot y_0^2+zz_0-z_0^2=0
$$
$$
xx_0+yy_0+zz_0=x_0^2+y_0^2+z_0^2
$$
$$
xx_0+yy_0+zz_0=a^2
$$



