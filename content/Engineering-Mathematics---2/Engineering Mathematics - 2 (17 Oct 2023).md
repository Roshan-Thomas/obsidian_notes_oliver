---
title: Lecture 7
date: 17 Oct 2023
---

**Worked Example 3.3**

Find scalar functions $\phi$ whose gradients $\vec\nabla\phi$ are 
$$
\vec v=(2x,4y,8z)
$$
**Solution**

$$
=\left(\frac{\partial\phi}{\partial x},\frac{\partial \phi}{\partial y},\frac{\partial\phi}{\partial z}\right)
$$
$$
\frac{\partial\phi}{\partial x}=2x\implies \phi=\int dx(2x)=x^2+f(y,z)
$$
$$
\frac{\partial\phi}{\partial y}=4y\implies \phi=\int dy(4y)=2y^2+g(x,z)
$$
$$
\frac{\partial\phi}{\partial z}=8z\implies\phi=\int dz(8z)=4z^2+h(x,y)
$$
$$
\therefore\phi(x,y,z)=x^2+2y^2+4z^2+c
$$
# Rules of vector differentiation
1. Linearity
$$
\text{grad }(\alpha f+\beta g)=\alpha\vec\nabla f+\beta\vec\nabla g
$$
$$
\text{div }(\alpha\vec u+\beta\vec v)=\alpha\vec\nabla\cdot u+\beta\vec\nabla\cdot\vec v=a\text{ div }\vec u+\beta\text{ div }\vec v
$$
$$
\text{curl }(\alpha\vec u+\beta\vec v)=\alpha\vec\nabla\times\vec u+\beta\vec\nabla\times\vec v=\alpha\text{ curl }\vec u+\beta\text{ curl }\vec v
$$
2. Product rules
$$
\text{grad }(fg)-\vec\nabla(fg)=f\nabla g+g\nabla f
$$
$$
\text{div }(fv)=\nabla\cdot(fv)=f\vec\nabla\cdot\vec v+\vec\nabla f\cdot\vec v
$$
$$
\text{curl }(fv)=\vec\nabla\times(fv)=f\nabla\times\vec v+\vec\nabla f\times\vec v
$$
3. Vector product rule
$$
\text{div }(\vec u\times\vec v)=\vec v\cdot\text{ curl }\vec u
$$

**Note:** Worked Example 3.4's answer is there at the end of the lecture notes on Blackboard (Page 18)

# Second derivatives
Second derivatives is if you do $\text{div}$, $\text{grad}$ or $\text{curl}$ twice. 

Out of 9 possibilities, only a few of them makes sense and can be used, and have engineering relevance to them.
You cannot do:
$$
\begin{align*}\text{grad grad }\phi&\\ \text{div div }\vec v&\\\text{grad curl }\vec v&\\ \text{curl div }\vec v\end{align*}
$$
Ones that are possible are:
$$
\begin{align*}\text{curl grad }\phi&=\vec\nabla\times(\vec\nabla\phi)\equiv 0\\ \text{div curl }\vec v&=\vec\nabla\cdot(\vec\nabla\times\vec v)\equiv0\end{align*}
$$
$$
\begin{align*}\text{div grad }\phi&:=\vec\nabla^2\phi\,\, &\text{(=Laplacian 'del-squared')} \\ \text{grad div }\vec v&=\vec\nabla(\vec\nabla\cdot \vec v)\,\, &\text{vector}\\ \text{curl curl }\vec v&=\vec\nabla\times(\nabla\times\vec v)\,\, &\text{vector} \end{align*}
$$

- The Laplacian is **very important**, as it comes up often in Physics.


**Note:**
	If you write $\vec\nabla^2\vec v$ it means you are acting on the entire Cartesian coordinates (x,y,z).

**Note:** Worked Example 3.6's answer is there at the end of the lecture notes on Blackboard (Page 19)
