---
title: Lecture 5
date: 23 Feb 2024
---
$$
v=p^2
$$
$$
\langle p,q\rangle=p(0)q(0)+p(1)q(1)+p(2)q(2)
$$
$$
B=\{1,x,x^2\}
$$
Let's take each element of the basis
$$
\bar v_1=1\,\,\,\,\,\,\,\,\,\, ||\bar v_1||^2=\langle \bar v_1,\bar v_1\rangle=1^2+1^2+1^2=3
$$
$$
\bar v_2=x-\frac{\langle 1,x\rangle}{||\bar v_1||^2}(1)=x-\frac{x|_0+x|_1+x|_2}{||\bar v_1||^2}(1)=x-\frac 3 3\times 1=x-1
$$
$$
\begin{split}\bar v_3&=x^2-\frac{\langle x^2,x-1\rangle}{||x-1||^2}(x-1)-\frac{\langle x^2,1\rangle}{||1||^2}1\\&=x^2-\frac 4 2(x-1)-\frac 5 3\times 1\\&=x^2-2x+\frac 1 3 \end{split}
$$
We want to use these polynomials to approximate the function $f=\cos x$
$$
p=\sum_{i=0}^2 a_ip_i\,\,\,\,\,\,\,\, a_i=\frac{\langle f,p_1\rangle}{||p_i||^2}
$$
$$
p_0=1,\, p_1=x-1,\, p_2=x^2-2x+\frac 1 3
$$
$$
a_0=\frac{\langle\cos x,1\rangle}{||1||^2}=\frac{\cos x|_0+\cos x|_1+\cos x|_2}{3}=\frac{1+\cos 1+\cos 2}{3}
$$
$$
\begin{split}a_1&=\frac{\langle \cos x,x-1\rangle}{||x-1||^2}=\frac{(\cos x)(x-1)|_0+(\cos x)(x-1)|_1+(\cos x)(x-1)|_2}{2}\\&=\frac{-\cos 0+\cos 2}2\\&=\frac{\cos 2-1}2\end{split}
$$
$$
\begin{split}||x^2-2x+\frac 1 3||^2&=\left.(x^2-2x+\frac 1 3)^2\right|_0+\left.(x^2-2x+\frac 1 3)^2\right|_1+\left.(x^2-2x+\frac 1 3)^2\right|_2\\&=\left(\frac 1 3\right)^2+\left(-\frac 2 3\right)^2+\left(\frac 1 3\right)^2\\&=\frac 6 9=\frac 2 3  \end{split}
$$
$$
\begin{split}a_2&=\frac{\langle\cos x,x^2-2x+\frac 1 3\rangle}{||x^2-2x+\frac 1 3||^2}\\&= \frac 1 2 -\cos 1+\frac 1 2 \cos 2\end{split}
$$

$$
\cos x\approx\frac{1+\cos 1+\cos 2}{3}\times 1+\frac{\cos 2-1}2(x-1)+\left(\frac 1 2-\cos 1+\frac \cos 2\right)\left(x^2-2x+\frac 1 3\right)
$$
Depending on your inner product, you will approximate different parts of the function. This inner product we just did does a good approximation for points at 0,1, and 2 but everywhere else its not good. But the Chebyshev approximation does a good approximation from -1 to 1, because it takes an integral from -1 to 1, and everywhere else its bad. So your choice of inner product affects the approximation you get. 
# Linear Functions, Dual Space, and Base Change
- Linear transforms will always consider the vector space and map it back to the vector space itself
$$
V\rightarrow V
$$
- Linear operators means that $V$ is a function space
	- Example: derivatives

**Dual Space** is the set of all linear functions that takes our vector space and maps it to the real numbers
$$
V^*:\text{ set of all }\mathcal{L}(V,R)
$$

#### Example
Consider a linear map that takes a 2D vector and takes it into another 2D vector
$$
T\left(\begin{bmatrix}x\\y\end{bmatrix}\right)=\begin{bmatrix}x-4y\\-2x+3y\end{bmatrix}\,\,\,\, R^2\rightarrow R^2
$$
Find the matrix representation of T
$$
\text{in }\begin{bmatrix}2\\0\end{bmatrix}\begin{bmatrix}0\\3\end{bmatrix}\,\,\,\,\text{ to }\begin{bmatrix}1\\1\end{bmatrix}\begin{bmatrix}-1\\1\end{bmatrix}
$$
We consider $T[\bar v_i]$
$$
T\left(\begin{bmatrix}2\\0\end{bmatrix}\right)=\begin{bmatrix}2\\-2\times 2\end{bmatrix}=\begin{bmatrix}2\\-4\end{bmatrix}=1\begin{bmatrix}2\\0\end{bmatrix}-\frac 4 3\begin{bmatrix}0\\3\end{bmatrix}
$$
$$
T\left(\begin{bmatrix}0\\3\end{bmatrix}\right)=\begin{bmatrix}-12\\0+9\end{bmatrix}=\begin{bmatrix}-12\\0\end{bmatrix}=-6\begin{bmatrix}2\\0\end{bmatrix}+3\begin{bmatrix}0\\3\end{bmatrix}
$$
$$
\begin{split}\mathcal{M}_{\bar v}(T)&=\left[T(\bar v_1); T(\bar v_2)\right]\\&=\begin{bmatrix}1&-6\\-\frac 4 3&3\end{bmatrix} \end{split}
$$
This gives us
$$
T\left(\begin{bmatrix} x\\y\end{bmatrix}\right)=\begin{bmatrix}x-4y\\-2x+3y\end{bmatrix}
$$
$$
T\left(\begin{bmatrix}1\\1\end{bmatrix}\right)=\begin{bmatrix}1-4\\-2+3\end{bmatrix}=\begin{bmatrix}-3\\1\end{bmatrix}=-\begin{bmatrix}1\\1\end{bmatrix}+2\begin{bmatrix}-1\\1\end{bmatrix}
$$
$$
T\left(\begin{bmatrix}-1\\1\end{bmatrix}\right)=\begin{bmatrix}-1-4\\2+3\end{bmatrix}=\begin{bmatrix}-5\\5\end{bmatrix}=5\begin{bmatrix}-1\\1\end{bmatrix}
$$
$$
\mathcal{M}_{\bar w}(T)=\begin{bmatrix}-1&0\\2&5\end{bmatrix}
$$
How are $\mu_{\bar v}$ and $\mu_{\bar w}$ related?

We can write any vector
$$
q=a_1\bar v_1+a_2\bar v_2=b_1\bar w_1+b_2\bar w_2
$$
Alternatively writing in matrix form
$$
\begin{bmatrix}\bar v_1&\bar v_2\end{bmatrix}\begin{bmatrix}a_1\\a_2\end{bmatrix}=\begin{bmatrix}\bar w_1&\bar w_2\end{bmatrix}\begin{bmatrix}b_1\\b_2\end{bmatrix}
$$
$$
\begin{bmatrix}2&0\\0&3\end{bmatrix}\begin{bmatrix}a_1\\a_2\end{bmatrix}=\begin{bmatrix}1^-1\\1&1\end{bmatrix}\begin{bmatrix}b_1\\b_2\end{bmatrix}
$$
$$
\begin{bmatrix}1&0\\0&1\end{bmatrix}\begin{bmatrix}a_1\\a_2\end{bmatrix}=\begin{bmatrix}\frac 1 2&-\frac 1 2\\\frac 1 3&\frac 1 3\end{bmatrix}\begin{bmatrix}b_1\\b_2\end{bmatrix}
$$
$$
\bar a=S\bar b
$$
This is a base change of $w\mapsto \bar v$
The inverse of that basis is 
$$
S^{-1}=\begin{bmatrix}1&\frac 3 2\\-1&\frac 3 2\end{bmatrix}\,\,\,\,\text{base change }v\mapsto w
$$


$$
\mathcal{M}_w(T)=S^{-1}\mathcal{M}_v(T)\underbrace{S}_{\text{change input}}
$$
We change the input, apply a transformation and then change the output
When you run that calculation 
$$
\underbrace{\begin{bmatrix}1&\frac 3 2\\-1&\frac 3 2\end{bmatrix}}_{S^{-1}}\underbrace{\begin{bmatrix}1&6\\-\frac 4 3&3\end{bmatrix}}_{\mathcal{M}_v}\underbrace{\begin{bmatrix}\frac 1 2&-\frac 1 2\\\frac 1 3&\frac 1 3\end{bmatrix}}_S=\underbrace{\begin{bmatrix}-1&0\\2&5\end{bmatrix}}_{\mathcal{M}_w}
$$
#### Example
Matrix representation of a linear transformation in the basis of monomials $\{1,t,t^2\}$
$$
\mathcal{L}[x(t)]=\int_0^1 x(t-\tau)d\tau\,\,\,\,\,\,\,\,\, x\in P^2
$$

$$
\mathcal{L}[1]=\int_0^1 1 d\tau =[\tau]_0^1=1
$$
$$
\mathcal L [t]=\int_0^1(t-\tau)\, d\tau=\left[t\tau-\frac{\tau^2}2\right]_0^1=t-\frac 1 2
$$
$$
\mathcal L[t^2]=\int_0^1(t-\tau)^2\, d\tau=\left[-\frac{(t-\tau)^3}{3}\right]_0^1=-\frac{(t-\tau)^3}{3}+\frac{t^3}3=t^2-t+\frac 1 3
$$
Putting it into matrix form
$$
\begin{split}\mathcal M(\mathcal L)&=\begin{bmatrix}\mathcal L[1],\mathcal L[t],\mathcal L[t^2]\end{bmatrix}\\&=\begin{bmatrix}1&-\frac 1 2&\frac 1 3\\0&1&-1\\0&0&1\end{bmatrix}\end{split}
$$
____
