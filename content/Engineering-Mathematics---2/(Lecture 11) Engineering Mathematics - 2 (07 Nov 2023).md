---
title: Lecture 11
date: 07 Nov 2023
---
**Worked example 5.3**

Consider the integral 
$$
\int_{y=0}^4\int_{x=\sqrt y}^2(y+xy)dx\, dy
$$
We can rewrite the integrals as 
$$
\int_{y=0}^4\int_{x=\sqrt y}^2 f(x,y)dx\,dy
$$
Sketching the region of integration

![[Engineering-Mathematics---2/images/Pasted-image-20231107151602.png|400]]

We get the above the region of integration if we evaluate first in the x direction, and then the y-direction

If you want to integrate first in the y-direction, 
$$
\int_{x=0}^2\int_{y=0}^{x^2} f(x,y)dy\, dx
$$
The region of integration would be

![[Engineering-Mathematics---2/images/Pasted-image-20231107152005.png|400]]

Lets say, you want the top-half of the graph of $y=x^2$, then the integral will become
$$
\int_{x=0}^2\int_{y=x^2}^4 f(x,y)dy\, dx
$$
This integral is not the same as the above two integrals, its COMPLETLY different.
____
**Worked Example 5.4**

The region of interest is 
$$
R:\begin{cases}0\le x\le\sqrt{1-y^2}\\ 0\le y\le 1\end{cases}
$$
![[Engineering-Mathematics---2/images/Pasted-image-20231107153033.png|400]]

The mass $M$
$$
M=\int_{y=0}^1\int_{x=0}^{\sqrt{1-y^2}}1\, dx\,dy=\int_{y=0}^1[x\bigg\vert_{0}^{\sqrt{1-y^2}} dy
$$
$$
=\int_{y=0}^1 \sqrt{1-y^2}dy
$$
Lets assume that 
$$
y=\sin\theta
$$
And
$$
dy=\cos\theta\, d\theta
$$
Then, substitute in the integral
$$
=\int_{\theta=0}^{\frac\pi 2}\underbrace{\sqrt{1-\sin^2\theta}\,\cos\theta}_{\cos^2\theta}\, d\theta
$$
$$
=\frac{1}2 \int_{\theta=0}^{\frac{\pi}2}(1+\cos2\theta)\,d\theta
$$
$$
=\frac 1 2 \left[\theta+\frac{\sin 2\theta}{2}\right\vert_{0}^{\frac \pi 2}
$$
$$
=\frac \pi 4
$$
Instead of Cartesian coordinates, lets do the same problem in **polar coordinates** also

Mass 
$$
M=\int_{\theta=0}^{\frac \pi 2}\int_{r=0}^1 r\, dr\, d\theta=\int_{\theta=0}^{\frac\pi 2}d\theta\int_{r=0}^1 r\, dr=\frac{\pi} 2\cdot \frac 1 2
$$
$$
=\frac\pi 4
$$
This method of using the polar coordinates is easier to do than using cartesian coordinates, and this method works well for this problem because of the symmetric nature of the region of interest, and the spherical shape of it. 

___
**Worked example 5.8**

![[Engineering-Mathematics---2/images/Pasted-image-20231107155016.png|300]]

The volume $V$
$$
V=\int\int\int\, dx\, dy\, dz
$$