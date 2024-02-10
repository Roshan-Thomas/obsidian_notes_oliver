---
title: Lecture 6
date: 09 Feb 2024
---
# Worked Example 6.2
Solve the PDE 
$$
u_{tt}=c^2u_{xx}\,\,\,\,\,\,\,\, 0<x<\infty,\,\,t\ge 0\,\,\,\,\,\,\, x\in R^+
$$
with initial conditions
$$
\text{at $t=0$ }\,\,\,\begin{array}{c}u(x,0)=0\\u_t(x,0)=0\end{array}
$$
and boundary conditions 
$$
\text{at $x=0$ }\,\,\,\,u(0,t)=\sin\omega t\,\,\,\,\,\,t\ge0
$$

**Step 1:** State d'Alembert's solution
$$
u(x,t)=f(x-ct)+g(x+ct)
$$
**Step 2:** Apply the Initial conditions
$$
t=0\,\,\,\,\, \begin{array}{c}u(x,0)=f(x)+g(x)=0\\ u_t(x,0)=\left[-cf'(x-ct)+cg'(x+ct)\right]_{t=0}=-cf'(x)+cg'(x)\end{array}
$$
**Step 3:** Solve for $f$ and $g$
$$
f(x)=-g(x)\,\,\,\,\,\, x>0
$$
$$
cg'(x)+cg'(x)=0\,\,\,\,\,\,\, x>0
$$
$$
g'(x)=0\Rightarrow g(x)=k,\,\,\,\,\, x>0
$$
$$
f(x)=-k,\,\,\, x>0
$$
**Step 4:** Plug $f'$ and $g'$ back
$$
u(x,t)=f(\underbrace{x-ct}_0)+g(\underbrace{x+ct}_0)
$$
$$
x(x,t)=-k+k=0\,\,\,\,\,\, x>ct
$$
**Step 5:** Apply Boundary conditions
$$
x=0\,\,\,\,\,\,\begin{array}{c}u(0,t)=f(-ct)+g(ct)=\sin\omega t\end{array}
$$
Hence,
$$
f(-ct)=-k+\sin\omega t
$$ 
Lets define $T$
$$
T=-ct,\,\,\,\, t=-\frac T c
$$
Then,
$$
f(T)=-k+\sin\left(-\frac{\omega T}c\right)\,\,\,\,\,\, T<0
$$
**Step 6:** Putting it back together, only for $x<ct$
$$
\begin{split}u(x,t)=&f(\underbrace{x-ct}_{<0})+g(\underbrace{x+ct}_{>0})\\=&-k+\sin\left(-\frac{\omega(x-ct)}{c}\right)+k\end{split}
$$
Finally,
$$
u(x,t)=\begin{cases}\sin\left(-\frac{\omega(x-ct)}{c}\right)&\text{ if }<x\le ct\\ 0&\text{ if }x>ct\end{cases}
$$

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240210213251.png|500]]

This is one of the example where you had a semi-infinite domain.
## Extras: What if we had 2 Boundary conditions?
$$
u_{tt}=u_{xx}\,\,\,\,\,\,\,(c=1)
$$
Lets consider the boundary conditions
$$
\begin{array}{c}u(0,t)=0\\ u(\pi, t)=0\end{array}
$$
Our domain is 
$$
0<x,\pi\,\,\,\,\,\, t>0
$$

The initial conditions are
$$
\begin{array}{c}u(x,0)=\sin x\\ u_t(x,0)=0\end{array}
$$
Note: you can use any function you want as the initial conditions, it will still work out.

**Step 1:** Using d'Alembert solutions
$$
u(x,t)=f(x-t)+g(x+t)
$$
**Step 2:** Use initial conditions
$$
\begin{array}{c}u(x,0)=f(x)+g(x)=\sin x\\ u_t(x,0)=-cf'(x)+cg'(x)=0\end{array}
$$
**Step 3:** Solve for $f,g$
$$
f(x)=\sin x-g(x)\,\,\,\,\,\,\,\, f'(x)=\cos x-g'(x)
$$
$$
u_t(x,0)=0\Rightarrow -c(\cos x-g'(x))+cg'(x)=0
$$
Rearranging the above equation
$$
g'(x)=\frac 1 2 \cos x
$$
$$
g(x)=k+\frac 1 2 \sin x,\,\,\,\,\, 0<x<\pi
$$
**Step 4:** 
$$
u(x,t)=\frac 1 2 \sin (\underbrace{x-t}_{0<x-t<\pi})-k+k+\frac 1 2 \sin(\underbrace{x+t}_{x+t<\pi})
$$

The solution only works if $x<\pi-t$ and $x>t$.

**Step 5:** Apply boundary conditions
The reason we do this is to extend the domain (its too tiny)
$$
u(0,t)=f(-t)+g(t)=0\tag{*}
$$
$$
u(\pi,t)=f(\pi-t)+g(\pi+t)\tag{**}
$$
$$
f(x)=\frac 1 2 \sin x-k,\,\,\,\,g(x)=\frac 1 2 \sin x+k,\,\,\,\, 0<x<\pi
$$
$$
f(-t)+g(t)=0\Rightarrow \begin{array}{c}f(-t)=g(t)\,\,\,\,t=-\tau\\ f(\tau=-g(-\tau)\end{array}
$$
Doing this graphically,

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240210214802.png|500]]
$$
f(x)=\frac 1 2 \sin x-k\,\,\,\,\,\, x<\pi
$$
$$
g(x)=\frac 1 2 \sin x +k\,\,\,\,\,\, x>0
$$
$$
\begin{split}u(x,t)&=\frac 1 2 \sin(x-t)+\frac 1 2 \sin(x+t)\\&=\sin(x)\sin(t)\end{split}
$$
This is essentially the same as separation of variables

The domain is 
$$
0<x<\pi\,\,\,\,\,\,\, t\ge 0
$$



