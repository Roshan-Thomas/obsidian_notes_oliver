---
title: Lecture 5
date: 10 Oct 2023
---
# Differentiation of Vector Fields
There are two different notions of differentiation of vector fields: Divergence and Curl.
- Divergence
	- Every point in the vector field is proportional to $\vec r$. 
	- Divergence tells us how much a vector field is 'flowing-out' of a particular point 
	- Divergence gives us a scalar
$$
\text{div }\vec v=\vec\nabla\cdot\vec v
$$
- Curl
	- Every point in the vector field is proportional to $r\hat \theta$.
	- Curl tells how a particular vector field is rotating over a point. 
		- Imagine a whirlpool, and you want to find out what the flow of a particular point on the circumference of the whirlpool. To do that, you would calculate the curl to help you understand the flow of a point.
	- Curl gives us a vector
$$
\text{curl }\vec v=\vec\nabla\times\vec v
$$
## Divergence
- Gives a scalar
$$
\vec\nabla\cdot\vec\sigma=\frac{\partial}{\partial x}v_1+\frac{\partial}{\partial y}v_2+\frac{\partial}{\partial z}v_3
$$
## Curl
- Gives a vector
$$
\text{curl }\vec v=\nabla\times \vec v=\begin{vmatrix}\vec i&\vec j&\vec k\\ \frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\ v_1&v_2&v_3\end{vmatrix}
$$
$$
\nabla\times\vec v-\left(\frac{\partial v_3}{\partial y}-\frac{\partial v_2}{\partial x}\right)\vec i+\left(\frac{\partial v_1}{\partial z}-\frac{\partial v_3}{\partial x}\right)\vec j+\left(\frac{\partial v_2}{\partial x}-\frac{\partial v_1}{\partial y}\right)\vec k
$$
**Worked Example 3.1** Calculate the divergence and curl
$$
\vec v=(4xy,yz,x)
$$
**Solution:**
Calculating the divergence
$$
\vec\nabla\cdot\vec v=\left(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z}\right)\cdot(4xy,yz,x)
$$

$$
= 4y+z
$$
Calculating the curl
$$
\vec\nabla\times\vec v=\begin{vmatrix}\vec i&\vec j&\vec k \\\frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\ 4xy&yz&x \end{vmatrix}
$$
$$
\begin{align}=& \vec i(-y)-\vec j(1)+\vec k(-4x) \\ =&(-y,-1,-4x)\end{align}
$$
## Applications of Divergence and Curl
### Rigid body mechanics
Consider a rigid cube body $B$ and is rotating about a fixed axis. The angular velocity vector $\vec\omega$. The velocity field at position $\vec r$ from the axis is given by
$$
v(r)=\vec\omega\times r
$$
(See image in Lecture notes)
$$
\vec \omega=(\omega_1,\omega_2,\omega_3)
$$
$$
\vec r=(x,y,z)
$$
Then we can show that 
$$
\text{div }\vec v=0,\,\,\,\,\, \text{curl }\vec v=2\vec\omega
$$
$$
\vec v=\vec\omega\times\vec r=\begin{vmatrix}\vec i&\vec j&\vec k\\ 0&0&\omega\\ x&y&z\end{vmatrix}=(-\omega y,\omega x,0)
$$
Divergence
$$
\vec\nabla\cdot\vec v=\left(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z}\right)\cdot(-\omega y,\omega x,0)=0
$$
Curl
$$
\vec\nabla\times\vec v=\begin{vmatrix}\vec i&\vec j&\vec k\\ \frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\ =\omega y&\omega x&0\end{vmatrix}=2\vec \omega
$$
### Fluid Mechanics

#### Example A
(See image in page 5 of Lecture notes)

Linear simple shear flow (velocity)
$$
\vec v=\left(\frac{v}{d}y,0,0\right)
$$
Divergence of that flow
$$
\vec\nabla\cdot\vec v=\left(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z}\right)\cdot\left(\frac{v}dy,0,0\right)
$$
$$
= 0
$$
Divergence being zero means that the flow of the liquid is *incomprehensible*.


Curl of that flow
$$
\vec\nabla\times\vec v=\begin{vmatrix}\vec i&\vec j&\vec k\\ \frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\ \frac{v}d y&0&0 \end{vmatrix}
$$
$$
=\left(0,0,\frac{-v}d\right)
$$
As you move along the flow, you can see a circular rotation around that point because the flow below you is slower than you. 

