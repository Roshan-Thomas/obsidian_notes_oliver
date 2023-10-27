---
title: Lecture 10
date: 27 Oct 2023
---
**Worked Example 4.7**
$$
\phi=f(r),\,\,\,\,\,\, \text{where }r=|\vec r|
$$
The gradient
$$
\vec\nabla\phi=\left(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},\frac{\partial f}{\partial z}\right)
$$
$$
r=r(x,y,z)
$$
By the chain rule
$$
=\left(\frac{\partial f}{\partial r}\frac{\partial r}{\partial x},\frac{\partial f}{\partial r}\frac{\partial r}{\partial y},\frac{\partial f}{\partial r}\frac{\partial r}{\partial z}\right)
$$
$$
=\left(\frac{\partial f}{\partial r}\right)\left(\frac{\partial r}{\partial x},\frac{\partial r}{\partial y},\frac{\partial r}{\partial z}\right)
$$
$$
=\left(\frac{df}{dr}\right)\vec\nabla r
$$
So,
$$
r=(x^2+y^2+z^2)^{\frac 1 2}
$$
So, if you take
$$
\frac{\partial r}{\partial x}=\frac{1}2 \frac{2x}{(x^2+y^2+z^2)^{1/2}}=\frac{x}r
$$
$$
\frac{\partial r}{\partial y}=\frac{y}r
$$
$$
\frac{\partial r}{\partial z}=\frac{z}r
$$
Thus,
$$
\nabla r=\left(\frac{x}r,\frac{y}r,\frac z r\right)=\frac{1}r (x,y,z)
$$
$$
=\frac{\vec r}r=\hat r
$$
$$
\huge\boxed{\nabla\phi=\left(\frac{df}{dr}\right)\hat r=\vec F}
$$
# Section 5 - Integration of scalar fields over areas and volumes

**Worked Example 5.2**

Calculate the area of the triangle with vertices at $(x,y)=(1,3),(3,3),\text{ and }(3,7)$.

To calculate this, we have to use a double integral with the appropriate limits to calculate the area of the triangle.

![[Engineering-Mathematics---2/images/Pasted-image-20231027153203.png|400]]
$$
\int_{y=3}^7\int_{x=p(y)}^{q(y)=3}\, dx\, dy
$$
$$
p(x)\implies y=ax+b
$$
The hypotenuse of the triangle can be defined as the line 
$$
y=2x+1
$$
$$
x=p,\,\,\,\,\,\, y=y
$$
$$
y=2p+1
$$
So, 
$$
p(y)=\left(\frac{y-1}{2}\right)
$$
Thus, the double integral would be
$$
\int_{y=3}^7\int_{x=\cfrac{y-1}{2}}^3\, 1\,dx\, dy
$$
The geometry is given by the limits of the integral (the endpoints). The inner integral is the quantity that you are integrating in this area (or shape).

So calculating the inner x-integral
$$
\int_{x=\cfrac{y-1}{2}}^3\, dx=[x\bigg\vert_{\cfrac{y-1}2}^3=3-\frac{y-1}{2}
$$
$$
=\frac{7-y}2
$$

Calculating the outer integral
$$
\int_{y=3}^7\left(\frac{7-y}{2}\right)dy=4
$$

Case 2: If you take the integral on y-axis as  varying
![[Engineering-Mathematics---2/images/Pasted-image-20231027154648.png|400]]
$$
\int_{x=1}^3\int_{y=3}^{2x+1}\, dy\, dx
$$
**Worked example 5.3**

What is the region of integration?
$$
\int_{y=0}^4\int_{x=\sqrt{y}}^2(y+xy)dxdy
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231027155109.png|400]]

If you take the y as varying, then the integral will become
$$
\int_{x=0}^2\int_{y=0}^{x^2}(\,\,\,\,\,\,\,)dy\,dx
$$
