---
title: Lecture 9
date: 19 Apr 2024
---
# Planar Dynamical Systems
If you have a dynamical system which is linear and is represented as
$$
\bar{\dot x}=A\bar x
$$
and has an initial condition of $\bar x(0)=\bar x_0$
It can be written as 
$$
\bar x(t)=\exp(At)\bar x_0
$$
To represent $\exp(At)$,
$$
\text{If } A=PDP^{-1}
$$
$$
D=\begin{bmatrix}\lambda_1&&&\\&&\ddots\\&&&\lambda_n\end{bmatrix}
$$
If $A=SJS^{-1}$
$$
J=\begin{bmatrix}J_{\lambda_1}&&&\\&&\ddots\\&&&\dots\end{bmatrix}
$$
$$
J_{\lambda_1, 1}=\begin{bmatrix}\lambda^1&&&&0\\&\lambda^1\\&&\lambda^1\\&&&\ddots\\0&&&&\lambda\end{bmatrix}
$$
$$
\exp J=\begin{bmatrix}\exp J_{\lambda_1, 1}&\dots\\&\exp J_{\lambda_1, 2}\\&&\ddots\end{bmatrix}
$$
$$
\exp J_{\lambda_1,t}=\left.\begin{array}{cccc}e^{\lambda t}&te^{\lambda t}&\frac{t^2}2 e^{\lambda t}&\dots&\frac{t^n}{n!}\\&e^{\lambda t}\\&&e^{\lambda t}\\&&&\ddots\end{array}\right]e^{\lambda t}
$$
So,
$$
\bar x(t)=\exp(At)x_0=P\exp(Dt)P^{-1}\bar x_0
$$
the eigenvalues of $A$ decide on the dynamic

#### Example
$$
\ddot{x}+\frac g L\sin x=0
$$
This is a pendulum which is swinging with an angle of $x$ and length L.

We can rewrite the system as,
$$
\begin{array}{c}x_1=x\\x_2=\dot x_1\end{array}\,\,\,\,\,\,\,\kappa=\frac g L\,\,\,\,\,\begin{array}{c}\dot x_1=x_2\\\dot x_2=-\kappa\sin x_1\end{array}
$$
At equilibrium,
$$
\begin{array}{c}\dot x_1=0\\ \dot x_2=0\end{array}\,\,\,\,\,\begin{array}{c}x_0=0\\-\kappa\sin x_1=0\end{array}\,\,\,\,\,\,\,x_1=0\text{ OR }x_1=\pi
$$
The first equilibrium is going to be at the origin $(0,0)$
Around $x_1=0$, $\dot x_2=-\kappa(x_1+hot)=-\kappa x_1$

$$
\begin{bmatrix}\dot x_1\\\dot x_2\end{bmatrix}=\underbrace{\begin{bmatrix}0&1\\-\kappa&0\end{bmatrix}}_A\begin{bmatrix}x_1\\x_2\end{bmatrix}
$$
$$
\text{det}(A-\lambda I)=(-\lambda)(-\lambda)+\kappa=0\,\,\,\,\,\,\,\,\,\lambda^2+\kappa=0\,\,\,\,\,\,\lambda=\pm j\sqrt{\kappa}
$$
The eigenvalues are **purely** imaginary ($Re(\lambda)=0$)
- cycle around $(0,0)$

![[Applied_Linear_Algebra/images/Pasted_image_20240419122000.png|300]]

So,
$$
\begin{bmatrix}0&1\\-\kappa&0\end{bmatrix}\begin{bmatrix}+ve\\+ve\end{bmatrix}=\begin{bmatrix}+ve\\-ve\end{bmatrix}
$$
Checking another quadrant
$$
\begin{bmatrix}0&1\\-\kappa&0\end{bmatrix}\begin{bmatrix}+ve\\-ve\end{bmatrix}=\begin{bmatrix}-ve\\-ve\end{bmatrix}=\begin{bmatrix}\dot x_1\\\dot x_2\end{bmatrix}
$$
Doing the equilibrium at $(\pi,0)$
$$
\sin(x_1)=-(x-\pi)+h.o.t
$$
$$
\dot x_2=-\kappa\sin(x_1)\approx\kappa(x_1-\pi)+\dots
$$

$$
\tilde x_1=x_1-\pi\,\,\,\,\,\, \tilde x_2=x_2 
$$
$$
\begin{bmatrix}\dot{\tilde x_1}\\\dot{\tilde x_2}\end{bmatrix}=\underbrace{\begin{bmatrix}0&1\\\kappa&0\end{bmatrix}}_B\begin{bmatrix}\tilde x_1\\\tilde x_2\end{bmatrix}\,\,\,\,\,\,\,\,\,\tilde x_1=0=\tilde x_2\,\,\,\text{ is the equilibrium}
$$
$$
\text{det}(B-\lambda I)=\lambda^2-\kappa=0\,\,\,\,\,\,\,\,\,\,\,\begin{array}{c}\lambda_+=\sqrt\kappa\\\lambda_-=-\sqrt\kappa\end{array}
$$
Finding our eigenvectors,
$$
\bar v=\begin{bmatrix}v_1\\v_2\end{bmatrix}
$$
$$
\lambda=\sqrt\kappa\,\,\,\,\,\,\,\,\,\begin{bmatrix}0&1\\\kappa&0\end{bmatrix}\begin{bmatrix}v_1\\v_2\end{bmatrix}=\begin{bmatrix}\sqrt{\kappa} v_1\\\sqrt\kappa v_2\end{bmatrix}\,\,\,\,\,\, v_2=\sqrt \kappa v_1\,\,\,\,\,\bar v=\begin{bmatrix}1\\\sqrt \kappa\end{bmatrix}
$$
$$
\lambda=-\sqrt \kappa\,\,\,\,\,\,\,\,\,\,\,\bar w=\begin{bmatrix}1\\-\sqrt\kappa\end{bmatrix}
$$
![[Applied_Linear_Algebra/images/Pasted_image_20240419123353.png|400]]
#### Example
$$
\ddot x+c\dot x+kx=0
$$
This is a model of an elastoplastic material

![[Applied_Linear_Algebra/images/Pasted_image_20240419123844.png|150]]

Writing it as a family of differential equations
$$
\begin{array}{c}x_1=x\\x_2=\dot x_1\end{array}
$$
$$
\begin{array}{c}\dot x_1=x_2\\\dot x_2=-k x_1-cx_2\end{array}\,\,\,\,\,\,\begin{array}{c}(1)\\(2)\end{array}\,\,\,\,\,\begin{array}{c}\dot x_1=0=x_2\\-kx_1-cx_2=0\implies x_1=0\end{array}
$$

$(x_1,x_2)=(0,0)$
$$
\begin{bmatrix}\dot x_1\\\dot x_2\end{bmatrix}=\begin{bmatrix}0&1\\-k&-0\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}
$$
$$
\text{det}(A-\lambda I)=-\lambda(-c-\lambda)+k=\lambda^2+\lambda c+k=0
$$
$$
\lambda_{\pm}=\frac{-c\pm \sqrt{c^2-4k}}{2}
$$
*Case 1*: $c^2-4k>0$
$$
\lambda_+=\frac{-c+\sqrt{c^2-4k}}{2}<0
$$
$$
\lambda_-=\frac{-c-\sqrt{c^2-4k}}{2}<0
$$
$$
\lambda_+\rightarrow \bar v_+=\begin{bmatrix}\frac{-2}{-c+\sqrt{c^2-4k}}\\1\end{bmatrix}
$$
$$
\lambda_-\rightarrow \bar v_-=\begin{bmatrix}\frac{-2}{-c-\sqrt{c^2+4k}}\\1\end{bmatrix}
$$
Sketching it,

![[Applied_Linear_Algebra/images/Pasted_image_20240419124711.png|400]]

The above sketch is a stable node

*Case 2:* $c^2-4k<0$
$$
\lambda_\pm=-\frac{c}2\pm j\sqrt{4k-c^2}
$$
Considering the real part of complex eigenvalues
$$
\text{Re}(\lambda_\pm)=-\frac{c}2<0\,\,\,\,\leftarrow\text{ attracting}
$$
$$
\begin{bmatrix}0&1\\-k&-c\end{bmatrix}\begin{bmatrix}+ve\\+ve\end{bmatrix}=\begin{bmatrix}+ve\\-ve\end{bmatrix}
$$
For the other quadrant
$$
\begin{bmatrix}0&1\\-k&-0\end{bmatrix}\begin{bmatrix}-ve\\-ve\end{bmatrix}=\begin{bmatrix}-ve\\+ve\end{bmatrix}
$$
![[Applied_Linear_Algebra/images/Pasted_image_20240419125035.png|500]]

The above sketch is a stable spiral.

