---
title: Lecture 17
date: 28 Nov 2023
---
# Fourier Transforms
We use the Fourier transforms to convert from a signal from the time domain to a frequency domain. 

To find the frequency content of an arbitrary function $f(t)$, we truncate the function to $\frac{-T}{2}<t<\frac{T}{2}$, frequency analyse with a regular Fourier series, and take the limit $T\rightarrow \infty$.

- Line spectrum tells us the how much of importance each frequency has in the signal.

The main idea: Take a signal in the time domain, and sample each point in that signal. As you keep on increasing the number of samples close to $\infty$ we get the signal in the frequency domain $\omega$.

**Definition**: The Fourier Transform 
$$
\mathcal{F}[f(t)]=F(\omega)-\int_{-\infty}^\infty f(t)\, e^{-j\omega t}\, dt
$$
### Worked Example 2.1
Frequency analyse the non-periodic signal $f:\Re\rightarrow\Re$  
$$
f(t)=\begin{cases}e^{-\alpha\, t}&\text{for }t\ge0\\ 0&\text{otherwise}\end{cases}
$$
where $\alpha>0$
![[Engineering-Mathematics---2/images/Pasted-image-20231128151754.png]]

Calculate the Fourier series of $f(t)$
$$
F(\omega)=\mathcal{F}[f(t)]=\int_{-\infty}^\infty f(t)\, e^{-j\omega t}\, dt
$$
$$
=\int_0^\infty e^{-\alpha\, t}e^{-j\omega t}dt
$$
$$
=\int_0^\infty e^{-\alpha t-j\omega t}dt
$$
$$
=\int e^{-(\alpha+j\omega)t}dt
$$
$$
=\left[-\frac{1}{\alpha+j\omega}e^{-(\alpha+j\omega)t}\right]_{t=0}^{t=\infty}
$$
$$
=-\frac{1}{\alpha+j\omega}\left(\underbrace{0}_{\text{because }e^{-\alpha t}\rightarrow 0\text{ as }t\rightarrow \infty}-\overbrace{1}^{e^0=1}\right)
$$
$$
\boxed{F(\omega)=\frac{1}{\alpha+j\omega}}
$$
The Fourier Transform $F(\omega)$ is a *complex* function of frequency $\omega$.
- To visualize, plot 2 graphs versus $\omega$:
	- magnitude spectrum $|F(\omega)|$
	- phase spectrum $\arg(F(\omega))$

#### Recap (Engineering Maths 1)
We can write a complex number $z$ as 
$$
z=\underbrace{x+jy}_{\text{Cartesian form}}=\underbrace{Re^{j\theta}}_{\text{Polar form}}
$$
Argand diagram:

![[Engineering-Mathematics---2/images/Pasted-image-20231128153006.png|400]]
$$
R=\sqrt{x^2+y^2}=|z|\text{ (magnitude) }
$$
$$
\theta=\tan^{-1}\left(\frac{y}x\right)=\arg(z)
$$
___
Going back to the worked example 2.1

Fourier Transform $F(\omega)=\frac{1}{\alpha+j\omega}$

**Magnitude Spectrum**
$$
|F(\omega)|=\left|\frac{1}{\alpha+j\omega}\right|
$$
To simplify, we'll use:
$$
|z_1z_2|=|z_1|\cdot|z_2|
$$
$$
\left|\frac{z_1}{z_2}\right|=\frac{|z_1|}{|z_2|}
$$
So the magnitude spectrum,
$$
|F(\omega)|=\frac{|1|}{|\alpha+j\omega|}
$$
$$
\boxed{|F(\omega)|=\frac{1}{\sqrt{\alpha^2+\omega^2}}}
$$
To plot the graphs, we can understand from the equation that it is always positive, it is symmetric in $\omega$ (even function of $\omega$), and for huge $\omega$ it tends to $\frac{1}{|\omega|}$ as $\omega\rightarrow\pm\infty$
![[Engineering-Mathematics---2/images/Pasted-image-20231128153829.png]]

**Phase Spectrum**
$$
\arg(F(\omega))=\arg\left(\frac{1}{\alpha+j\omega}\right)
$$
To simplify, we use
$$
\arg(z,z_2)=\arg(z_1)+\arg(z_2)
$$
$$
\arg\left(\frac{z_1}{z_2}\right)=\arg(z_1)-\arg(z_2)
$$
So, to plot the phase spectrum
$$
\arg(F(\omega))=\underbrace{\arg(1)}_{=0}-\arg(\alpha+j\omega)
$$
$$
\boxed{\arg(F(\omega))=-\tan^{-1}\left(\frac{\omega}{\alpha}\right)}\approx-\frac{\omega}{\alpha}\text{ for }\omega\approx 0
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231128154524.png]]

Note: $\tan^{-1}(x)\backsimeq x$ for small $x$
