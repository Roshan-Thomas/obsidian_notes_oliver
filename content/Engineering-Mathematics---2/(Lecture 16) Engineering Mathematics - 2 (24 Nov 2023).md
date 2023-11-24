---
title: Lecture 16
date: 24 Nov 2023
---
Continued from [[(Lecture 15) Engineering Mathematics - 2 (21 Nov 2023)]].

**We have to calculate $a_0$ separately**

Substitute $n=0$ into the definition of the coefficients and then integrate
$$
a_0=\frac{2}{2}\int_{-1}^1 f(t)\,\cos(0)\, dt=\frac{2}{2}\int_{-1}^1\, f(t)\, dt
$$
$$
=\frac{2}{2}\cdot\frac{1}{2}\cdot 2\cdot 1
$$
$$
\boxed{a_0=1}
$$
**Now find the $b_n$ coefficients**
$$
b_n=\frac{2}{2}\int_{-1}^1 f(t)\, \sin(n\pi t)\, dt
$$
$$
=\int_{-1}^0 (1+t)\, \sin(n\pi t)\, dt+\int_{0}^1(1-t)\, \sin(n\pi t)dt
$$
$$
\boxed{b_n=0}
$$
Note: We know that $b_n=0$ because the function $f(t)$ is an even function. 
- Even functions are $f(-t)=f(t)$ for all $t$
	- It basically means that even functions when mirrored (vertically), the graph looks the same way. 
	- Even functions always have $b_n=0$ for all n. Fourier series with $\cos$ terms only.
- Odd functions are $f(-t)=-f(t)$ for all t
	- Odd functions always have $a_n=0$ for all n. Fourier series with sin terms only.

So, the Fourier Series for $f$ is
$$
\boxed{f(t)\backsim\underbrace{\frac{1}{2}}_{\frac{a_0}{2}}+\sum_{n=1}^\infty\underbrace{\frac{2}{(n\pi)^2}(1-\cos(n\pi\, t))}_{a_n}\underbrace{\cos(n\pi\, t)}_{\cos(n\omega t)}}
$$
From the line spectrum in Slide 12 (On Blackboard)
- we can see that there is no energy in the higher frequencies (only in the lower frequencies)
- We can see that there is NO effect by the even harmonics in the total energies. And, half of the Fourier coefficients are zero!

$$
\text{if n is even }\,\,\,\,\,\, n=2m\,\,\,\,\, \text{ for }m=1,2,3,\dots
$$
$$
\implies a_n=0\,\,\,\,\,\,\,\, 1-\cos(n\pi)=1-\cos(2m\pi)=1-1=0
$$
$$
\text{if n is odd }\,\,\,\,\,\,\,\,\,\, n=2m-1\,\,\,\,\text{ for }m=1,2,3,\dots
$$
$$
1-\cos(n\pi)=1-\cos((2m-1)\pi)
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231124152518.png|400]]
$$
a_n=\frac{2\cdot 2}{(2m-1)^2\pi^2}
$$
$$
\implies\boxed{f(t)\backsim\frac{1}{2}+\sum_{m=1}^\infty\frac{4}{(2m-1)^2\pi^2}\cos(2m-1)\pi\, t}
$$
The best Fourier Series 

# Frequency analysis of non-periodic function
- If you have a function $f(t)$ which is only defined for a finite period
	- One method that you can do is take that finite signal and repeat it over and over and apply the Fourier Series on it. 
	- Another Method is to extend your original signal into either a even (flipping on x axis) or into an odd (flipping on y axis) function, and then repeat it.
		- The benefit of this is that you will only need to deal with either $\cos$ terms or $\sin$ terms. 
		- This is called Fourier Half range series.

### Worked Example 1.4
$$
f:[0,4]\rightarrow\Re
$$
$f$ is defined on an interval of length $L=4$
$$
f(t)=\begin{cases}t,&0\le t\le2\\ 4-t,&2<t\le4\end{cases}
$$
Plotting the graph

![[Engineering-Mathematics---2/images/Pasted-image-20231124154423.png]]

Fourier series of $f_0(t)$ is the $\frac{1}{2}-$range  Fourier $\sin$ series
$$
f(t)\backsim\sum_{n=1}^\infty b_n\sin\left(\frac{n\pi\, t}{L}\right)
$$
$$
b_n=\frac{2}{L}\int_0^L\, f(t)\sin\left(\frac{n\pi\, t}{L}\right)\, dt
$$
$$
=\frac{2}{4}\int_0^4 f(t)\, \sin\left(\frac{n\pi t}{4}\right)\, dt
$$
$$
=\frac{1}{2}\left\{\int_0^2t\cdot\sin\left(\frac{n\pi\, t}{4}\right)\, dt+\int_2^4(4-t)\cdot\sin\left(\frac{n\pi\, t}{4}\right)\, dt\right\}
$$
Use integration by parts $\int uv'=uv-\int u'v$
$$
=\frac{1}{2}\left\{\left[t-\frac{4}{n\pi}\cos\left(\frac{n\pi\, t}{4}\right)\right]_0^2-\int_0^2 1-\frac{4}{n\pi}\cos\left(\frac{n\pi\, t}{4}\right)\, dt+  \left[(4-t)-\frac{4}{n\pi}\cos\left(\frac{n\pi\, t}{4}\right)\right]_2^4-\int_2^4-1-\frac{4}{n\pi}\cos\left(\frac{n\pi\, t}{4}\right)\, dt\right\}
$$
$$
=\frac{1}{2}\left\{\left(2-\frac{4}{n\pi}\cos\left(\frac{n\pi}{2}\right)-0\right)+\left(0-2-\frac{4}{n\pi}\cos\left(\frac{n\pi}{2}\right)\right)+\int_0^2\frac{4}{n\pi}\cos\left(\frac{n\pi\, t}{4}\right)\, dt-\int_2^4\frac{4}{n\pi}\cos\left(\frac{n\pi\, t}{4}\right)\, dt\right\}
$$
$$
=\left[\frac{8}{(n\pi)^2}\sin\left(\frac{n\pi\, t}{4}\right)\right]_0^2-\left[\frac{8}{(n\pi)^2}\sin\left(\frac{n\pi\, t}{4}\right)\right]_2^4
$$
$$
\boxed{b_n=\frac{16}{(n\pi)^2}\sin\left(\frac{n\pi}{2}\right)}
$$
$$
\implies \boxed{f(t)\backsim\sum_{n=1}^\infty\frac{16}{(n\pi)^2}\sin\left(\frac{n\pi}{2}\right)\cdot \sin\left(\frac{n\pi\, t}{4}\right)}
$$



