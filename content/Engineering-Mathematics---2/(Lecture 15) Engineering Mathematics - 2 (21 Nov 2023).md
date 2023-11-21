---
title: Lecture 15
date: 21 Nov 2023
---
# Linear Systems & Partial Differential Equations

## Periodic functions
- Periodic function $f(t)$ is a function which keep repeating over and over with a period of $T$. 
$$
\text{Frequency } \omega=\frac{2\pi}{T}
$$
## Fourier Series
A periodic function with a period $T$ can be represented as a Fourier series
$$
f(t)\backsim\frac{a_0}{2}+\sum_{n=1}^\infty \underbrace{a_n\cos(n\omega\, t)}_{\text{periodic functions}}+\underbrace{b_n\sin(n\omega\, t)}_{\text{periodic functions}}\tag{1}
$$
where $\omega=\frac{2\pi}{T}$, and $a_n, b_n$ are Fourier coefficients
- Every $n\omega$ there is some content/signal that builds up.
- Bigger the numbers $a_n, b_n$, bigger the signal.
$$
a_n=\frac{2}{T}\int_{-T/2}^{T/2}f(t)\cos(n\omega\, t)dt
$$
$$
b_n=\frac{2}{T}\int_{-T/2}^{T/2}f(t)\sin(n\omega\, t)dt
$$
- $\frac{a_0}{2}$ term in equation (1) helps removes the average value of zero or also known as the DC offset. 
- This Fourier series is almost always equal to the function $f(t)$ in equation (1). The only time it is not true is when the function is discontinuous (functions that jump from one point to another suddenly).
	- The reason for this is because both the terms in the Fourier series are continuous.
	- To fix this, you will have to calculate the Fourier series from both sides of the discontinuities.
### Line Spectrum
- helps visualise a Fourier Series
- frequency content is at different integer intervals $(-5\omega, -4\omega,\dots,0,\omega,\dots)$
- Heights are symmetric in the y-axis

### Worked Example 1.2
Find the Fourier series of the periodic function with period $T=2$, 
$$
f(t)=1-|t|,\,\,\,\,\,-1<t\le1
$$
Our first step would be to sketch the function
$$
|t|=\begin{cases}t&t>0\\ -t&t<0\end{cases}
$$
$$
f(t)=\begin{cases}1-t&0<t\le1\\1+t&-1<t<0\end{cases}
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231121153637.png]]

This function has a period of $T=2$ and keeps repeating to the right and left. 
$$
\omega=\frac{2\pi}{T}=\frac{2\pi}{2}=\pi
$$
$$
f(t)\backsim\frac{a_0}{2}+\sum_{n=1}^\infty a_n\cos(n\omega\, t)+b_n\sin(n\omega\, t)
$$
$$
a_n=\frac{2}{T}\int_{-T/2}^{T/2} f(t)\cos(n\omega\, t)dt
$$
$$
b_n=\frac{2}{T}\int_{-T/2}^{T/2}f(t)\sin(n\omega\, t)dt
$$
Calculating $a_n$
$$
a_n=\frac{2}{2}\int_{-1}^1 f(t)\cos(n\pi t)dt
$$
$$
=\int_{-1}^0 \underbrace{(1+t)}_{u}\underbrace{\cos(n\pi t)}_{v'}dt+\int_0^1(1-t)\cos(n\pi t)dt
$$
Using integration by parts we can evaluate the integrals
$$
\int uv'=uv-\int u'v
$$
$$
\implies \begin{align*}\left[\underbrace{(1+t)}_{u}\cdot\underbrace{\frac{1}{n\pi}\sin(n\pi t)}_v\right]_{-1}^0-\int \underbrace{1}_{u'}\cdot\underbrace{\frac{1}{n\pi}\sin(n\pi t)}_{v}dt\\+\left[\underbrace{(1-t)}_{u}\cdot\underbrace{\frac{1}{n\pi}\sin(n\pi t)}_{v'}\right]_{-1}^0-\int\underbrace{-1}_{u'}\cdot\underbrace{\frac{1}{n\pi}\sin(n\pi t)}_{v}dt\end{align*}
$$
$$
\begin{align*}=\left(1\cdot\frac{1}{n\pi}\sin(0)-0\cdot\frac{1}{n\pi}\sin(-n\pi)\right)+\left(0\cdot\frac{1}{n\pi}\sin(n\pi)-1\cdot\frac{1}{n\pi}\sin(0)\right)\\-\int_{-1}^0\frac{1}{n\pi}\sin(n\pi t)dt+\int_{0}^1\frac{1}{n\pi}\sin(n\pi t)dt\end{align*}
$$
$$
=\left[\frac{1}{(n\pi)^2}\cos(n\pi t)\right]_{-1}^0+\left[-\frac{1}{(n\pi)^2}\cos(n\pi t)\right]_0^1
$$
$$
=\frac{1}{(n\pi)^2}(\cos(0)-\cos(-n\pi))-\frac{1}{(n\pi)^2}(\cos(n\pi)-\cos(0))
$$
$$
a_n=\frac{2}{(n\pi)^2}(1-\cos(n\pi))
$$
To be continued in Friday's Lecture...
