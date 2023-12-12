---
title: Lecture 20
date: 12 Dec 2023
---
# Fourier series of even and odd functions
- If $f(t)$ is an even function then
$$
f(t)\backsim\frac{a_0}{2}+\sum_{n=1}^\infty a_n\cos(n\omega t)
$$

$$
b_n=0
$$
and
$$
a_n=\frac{4}T \int_0^{T/2}f(t)\,\cos(n\omega t)\, dt
$$
- If $f(t)$ is an odd function then
$$
f(t)\backsim\sum_0^\infty b_n\sin(n\omega t)
$$
$$
a_n=0
$$
$$
b_n=\frac{4}T\int_0^{T/2}f(t)\sin(n\omega t)\, dt
$$
## Quick Quiz #2
We have a signal
$$
f(t)=\begin{cases}\cos(t)&0\le t\le\frac{\pi}2\\ 0&\frac{\pi}2\le t\le\pi\end{cases}
$$
$$
f:[0,\pi]\rightarrow \mathcal{R}
$$
This signal is defined on a finite-length interval in time $L=\pi$

We can't calculate its Fourier Series (atleast not directly) because its not periodic

To do so we have to extend its definition to make it *periodic*

**Plot the even and odd periodic extensions**

![[Engineering-Mathematics---2/images/Pasted-image-20231212151944.png]]

To make the even signal, we reflect the function $f(t)$ in the y-axis

To make the odd signal, we reflect the function $f(t)$ in the x-axis and y-axis

![[Engineering-Mathematics---2/images/Pasted-image-20231212152151.png]]

The period is generally taken as $T=2L$, so the even and odd functions when repeated would look like,

![[Engineering-Mathematics---2/images/Pasted-image-20231212152517.png]]
____
## Worked Example 1.2
We calculated the Fourier coefficients, and 
$$
a_0=1,\,\,\,\, \underbrace{a_n=\frac{2(1-(-1)^n)}{(n\pi)^2},\,\,\,\,\,\, b_n=0}_{n\ge 1}
$$
$$
\implies f(t)\backsim\frac{1}{2}+\sum_{n=1}^\infty \frac{2(1-(-1)^n)}{(n\pi)^2}\cos(n\pi t)
$$
Can we do better? Yes!!
$$
\begin{rcases}\begin{array}{c c}n&a_n\\1&\frac{2}{\pi^2}(1--1)=\frac{2}{\pi^2}\cdot 2\\ 2&\frac{2}{(2\pi)^2}(1-1)=\frac{2}{(2\pi)^2}\cdot 0=0 \\ 3 & \frac{2}{(3\pi)^2}(1--1)=\frac{2}{(3\pi)^2}\cdot 2\\ 4 & \frac{2}{(4\pi)^2}(1-1)=\frac{2}{(4\pi)^2}\cdot 0=0 \end{array}\end{rcases}\text{ suggests that n is even }\implies a_n=0
$$
$n$ even
$$
n=2,4,6,8,\dots\,\,\,\,\,\,\,\,\text{ i.e. }n=2m\,\,\,\,\,\,\, m=1,2,3,4,\dots
$$
$$
a_n=\frac{2}{(n\pi)^2}\underbrace{(1-\underbrace{(-1)^{2m}}_{=1})}_0=0
$$
$n$ odd
$$
n=1,3,5,7,\dots\,\,\,\,\,\,\,\,\, \text{ i.e. } n=2m-1\,\,\,\,\,\,\, m=1,2,3,4,\dots
$$
$$
a_n=\frac{2}{(n\pi)^2}\underbrace{(1-\underbrace{(-1)^{2m-1}}_{-1})}_{2}=\frac{4}{(n\pi)^2}
$$
So, a better Fourier series is
$$
f(t)\backsim\frac{1}{2}+\sum_{m=1}^\infty \frac{4}{(2m-1)^2\pi^2}\cdot\cos\underbrace{((2m-1)\pi t)}_{\text{only add harmonics}}
$$
____
Note: Have a look through the Worked Example 1.4 shown in [[(Lecture 16) Engineering Mathematics - 2 (24 Nov 2023)]]

___
## $\cos/\sin$ shortcuts
This happens when $n$ is an integer 
$$
\cos(n\pi)=(-1)^n
$$
$$
\sin(n\pi)=0
$$
The above formulae can easily be shown by the graph of a $\sin$ and $\cos$ function
