---
title: Lecture 21
date: 15 Dec 2023
---
# Revision
- There is not a way to visualize the result of Laplace Transforms (currently).

## Homework Week 10
Frequency analyse the signal
$$
u(t)=e^{-\alpha|t-t_0|}\,\,\,\,\,\,\, t\in \Re
$$
$$
\alpha>0\text{ constant }, t_0\text{ constant }
$$
Find the Fourier Transform
$$
U(W)=\mathcal{F}[u(t)]=\int_{-\infty}^\infty u(t)e^{-j\omega t}\, dt
$$
and then plot (versus $\omega$)
- magnitude spectrum $|U(w)|$
- phase spectrum $\arg(U(w))$

We could substitute $u(t)$ into the definition and calculate $U(\omega)$

Instead, define 
$$
f(t)=e^{-\alpha|t|},\,\,\,\,\,\, t\in\Re
$$
So,
$$
u(t)=f(t-t_0)=e^{-\alpha|t-t_0|}
$$
In a time-delay signal, using the FT time-delay property
$$
U(\omega)=\mathcal{F}[u(t)]
$$
$$
=\mathcal F [f(t-t_0)]
$$
$$
=e^{-j\omega t_0}\mathcal F[f(t)]
$$
$$
=e^{-j\omega t_0}\mathcal F(\omega)
$$
So,
$$
F(\omega)=\mathcal{F}[f(t)]=\int_{-\infty}^\infty e^{-\alpha|t|}e^{-j\omega t}\, dt
$$
$$
|t|=\begin{cases}t&t>0\\ -t&t<0\end{cases}
$$
$$
e^{-\alpha|t|}=\begin{cases}e^{-\alpha t}&t>0\\ e^{\alpha t}&t<0\end{cases}
$$
Therefore,
$$
F(\omega)=\int_{-\infty}^0 e^{\alpha t}e^{-j\omega t}\, dt+\int_0^\infty e^{-\alpha t}e^{-j\omega t}\, dt
$$
$$
=\int_{-\infty}^0 e^{(\alpha-j\omega)t}\, dt+\int_0^\infty e^{-(\alpha+j\omega)t}\, dt
$$
$$
=\left[\frac{1}{\alpha-j\omega}e^{(\alpha-j\omega)t}\right]_{-\infty}^0+\left[-\frac{1}{\alpha+j\omega}e^{-(\alpha+j\omega)t}\right]_0^\infty\tag{$\int e^{kt}=\frac{1}{k}e^{kt} $}
$$
$$
=\frac{1}{\alpha-j\omega}(1-0)-\frac{1}{\alpha+j\omega}(0-1)
$$
$$
=\frac{1}{\alpha-j\omega}+\frac{1}{\alpha+j\omega}
$$
$$
=\frac{\alpha+j\omega+\alpha-j\omega}{(\alpha-j\omega)(\alpha+j\omega)}
$$
$$
\boxed{F(\omega)=\frac{2\alpha}{\alpha^2+\omega^2}}
$$
Plugging into our time-shifting result, 
$$
\boxed{U(\omega)=e^{-j\omega t_0}\cdot\frac{2\alpha}{\alpha^2+\omega ^2}}
$$
**Plotting the Magnitude Spectrum**
$$
|U(\omega)|=\left|e^{-j\omega t_0}\cdot\frac{2\alpha}{\alpha^2+\omega^2}\right|
$$
$$
=\underbrace{\left|e^{-j\omega t_0}\right|}_{1}\cdot \underbrace{\frac{|2\alpha|}{|\alpha^2+\omega^2|}}_{\text{real, positive numbers}}
$$
$$
|U(\omega)|=\frac{2\alpha}{\alpha^2+\omega^2}
$$
We know about the function $|U(\omega)|$
- when $\omega=0$, $|U|=\frac{2}\alpha$
- $|U|\ne 0$ for all $\omega$
- $|U|$ is an even function of $\omega$
- $\omega\rightarrow\pm \omega$, $|U|\rightarrow\frac{2\alpha}{\omega^2}\rightarrow0$

![[Engineering-Mathematics---2/images/Pasted-image-20231215152642.png|500]]

**Plotting the Phase Spectrum**
$$
\arg\left(U(\omega)\right)=\arg\left(\underbrace{\frac{2\alpha}{\alpha^2+\omega^2}}_{R>0}\cdot \underbrace{e^{-j\omega t_0}}_{e^{j\theta}}\right)=-\omega t_0
$$
which is proportional to $\omega$, so its a straight line.

![[Engineering-Mathematics---2/images/Pasted-image-20231215153045.png|500]]

## Quick Quiz #1 
Rectangular pulse function
$$
r(t)=\begin{cases}1&\text{for }-1\le t\le 1\\ 0&\text{otherwise}\end{cases}
$$
The Fourier Transform
$$
R(\omega)=\mathcal F[r(t)]=\frac{2\sin\omega}{\omega}
$$
(which can be found by plugging in the pulse function into the definition of Fourier Transform)

**Magnitude Spectrum**
$$
|R(\omega)|=\left|\frac{2\sin\omega}{\omega}\right|=\frac{2|\sin\omega|}{|\omega|}
$$
We know about the function
- when $\omega=0$, $\lim_{x\rightarrow 0}\frac{\sin x}{x}=1$, and $|R|=2$ at $\omega=0$
- $|R|=0$ when $\sin\omega=0\Leftrightarrow\omega=n\pi\,\,\,\,\,n\in Z$
- when $\omega\rightarrow\pm \infty$, then $|R|\rightarrow 0$

![[Engineering-Mathematics---2/images/Pasted-image-20231215153807.png]]

The decreasing envelope is proportional to $\frac{2}{|\omega|}$.

**Phase Spectrum**
$$
\arg\left(\underbrace{\frac{2\sin\omega}{\omega}}_{Re^{j\theta}}\right)
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231215154147.png|400]]
$$
=\begin{cases}0&\text{if }\frac{\sin\omega}{\omega}>0\\ \pi &\text{if }\frac{\sin\omega}{\omega}<0\end{cases}
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231215154304.png]]






