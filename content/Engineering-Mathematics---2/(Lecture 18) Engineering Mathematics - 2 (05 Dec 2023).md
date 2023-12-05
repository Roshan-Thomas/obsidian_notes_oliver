---
title: Lecture 18
date: 05 Dec 2023
---
# Laplace transforms
From the time domain we can go to the Laplace domain using the Laplace transform and then convert back into the time domain using the inverse Laplace transform.

The Laplace transform of a function $f(t)$ is
$$
L[f(t)]=F(s)=\int_0^\infty e^{-st}f(s)\, dt
$$
Taking the inverse 
$$
L^{-1}[F(s)]=f(t)
$$
but there is no simple expression for $L^{-1}$, we need to use lookup tables for the inverse Laplace transform.

- Laplace and Fourier transforms have lots of similarities
$$
\text{Fourier: }\mathcal{F}[f(t)]=\int_{-\infty}^\infty e^{-j\omega t}f(t)\, dt
$$
$$
\text{Laplace: }L[f(t)]=\int_0^\infty e^{-st}f(t)\, dt
$$
- The oscillating $e^{-j\omega t}$ is replaced by a decaying $e^{-st}$ (if Re(s) $>0$), so that means that Laplace can deal with signals that dont have finite energy.
- The lower limit of integration is changed in the Laplace Transform, so that means the Laplace Transform is for processes that move forward in time.
- There is no direct analogue of the magnitude and phase spectra for Laplace Transform.
## Transforms of common functions
$$
L[1]=\frac{1}{s}
$$
$$
L[t^n]=\frac{n!}{s^{n+1}}
$$
These two above functions assumes that $(Re(s)>0)$
$$
L[e^{-at}]=\frac{1}{s+a}
$$
$$
L[\cos(\omega t)]=\frac{s}{s^2+\omega^2}
$$
$$
L[\sin(\omega t)]=\frac{\omega}{s^2+\omega^2}
$$
- These functions can either be calculated by integration using the formula at the top, or you can use the formula sheet to look up the specific Laplace Transform of common functions. 
## Properties of Laplace Transform
- The Laplace transform is linear
$$
L[af(t)+bg(t)]=aL[f(t)]+bL[g(t)]
$$
- Derivative of a Laplace Transform, if $F(s)=L[f(t)]$
$$
L[tf(t)]=-\frac{dF}{ds}
$$
$$
L[t^nf(t)]=(-1)^n\frac{d^nF}{ds^n}
$$
### Worked Example 3.1
Find the Laplace Transform of
$$
t^2(1+\sin(\omega t))
$$
$$
L[t^2(1+\sin(\omega t))]
$$
$$
=L[t^2+t^2\sin(\omega t)]
$$
Using linearity,
$$
=\underbrace{L[t^2]}_{\text{standard result}}+\underbrace{L[t^2\sin(\omega t)]}_{\text{use L.T. of }t^n f(t)}
$$
$$
=\frac{2!}{s^3}+(-1)^n\frac{d^2}{ds^2}\underbrace{L[\sin(\omega t)]}_{\text{standard result}}
$$
$$
=\frac{2!}{s^3}+1\cdot\frac{d^2}{ds^2}\left(\frac{\omega}{s^2+\omega^2}\right)\tag{1}
$$
using quotient rule for the second term, and isolating the second term
$$
=\frac{d}{ds}\left(\frac{d}{ds}\left(\frac{\omega}{s^2+\omega^2}\right)\right)
$$
$$
=\frac{d}{ds}\left(\frac{0-\omega\cdot 2s}{(s^2+\omega^2)^2}\right)
$$
$$
=-\frac{d}{ds}\left(\frac{2\omega s}{(s^2+\omega^2)^2}\right)
$$
$$
=-\left(\frac{2\omega\cdot(s^2+\omega^2)-2\omega s\cdot 2(s^2+\omega^2)\cdot 2s}{(s^2+\omega^2)^2}\right)
$$
$$
=-\frac{2\omega}{(s^2+\omega^2)^2}+\frac{8\omega s^2}{(s^2+\omega^2)^3}
$$

Substituting back in Equation (1)
$$
\boxed{\implies L\left[t^2(1+\sin(\omega t))\right]=\frac{2}{s^3}-\frac{2\omega}{(s^2+\omega^2)^2}+\frac{8\omega s^2}{(s^2+\omega^2)^3}}
$$
N.B We also now know that 
$$
L^{-1}\left[-\frac{2\omega}{(s^2+\omega^2)^2}+\frac{8\omega s^2}{(s^2+\omega^2)^3}\right]=t^2\sin(\omega t)
$$
___
- The reason we do Laplace transform is because it is tool we can use to solve ODEs. 
## Solving ODEs with Laplace Transform
The method
- Take the Laplace transform of the ODE
- Solve for the Laplace transform of the output
- Simplify it until you have recognizable parts
- using your knowledge, and Laplace transform tables, invert the transform.


Note: Differentiation in the time domain, is just multiplication by s plus a polynomial in the s-domain (Laplace domain). The alternative is also true, differentiation in the s-domain is essentially a multiplication in the time domain.