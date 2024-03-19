---
title: Lecture 15
date: 19 Mar 2024
---
# Covariance, Correlation, Linear Regression
## Covariance
Covariance tells us the direction of relationship between two variables.

Sample covariance matrix
$$
Q=\frac{1}{n-1}\sum_{i=1}^n (u_i-\bar u)(u_i-\bar u)^T
$$
where $n$ is the number of samples, and $u_i$ is the column vector with m elements.
## Correlation
Similar to covariance, but correlation values are from -1 to 1. 

Sample correlation coefficient
$$
r=\frac{\sum_{i=1}^n(X_i-\bar x)(Y_i-\bar y)}{\sqrt{\sum_{i=1}^n(X_i-\bar x)^n}\sqrt{\sum_{i=1}^n(Y_i-\bar y)^2}}
$$

We make a bunch of assumptions, and the chief one among them are that the covariance and correlation vary linearly. 

## Linear Regression
It is a means to estimate the parameters of a model.

Normal equations for a straight line
$$
\begin{array}{c}\beta_1 n+\beta_2\sum_{i=1}^n x_i=\sum_{i=1}^n y_i\\ \beta_1\sum_{i=1}^n x_i+\beta_2\sum_{i=1}^n x_i^2=\sum_{i=1}^n x_iy_i\end{array}
$$
## Exercise 1
(See question in slide 8 on Blackboard)

Information from the question
$n=7$ (number of samples)
$H_o$ - no corellation, $\therefore$ $rho=0$
$r=-0.8890$

Use the Fisher transformation (converted to standard normal)
$$
\left[\frac{1}2\ln\left(\frac{1+r}{1-r}\right)-\frac 1 2\ln\left(\frac{1+\rho}{r-\rho}\right)\right]\sqrt{n-3}\backsim \mathbb{N}(0,1)
$$
Calculate the value of the test statistic
$$
\left[\frac 1 2\ln\left(\frac{1-0.8890}{1+0.8890}\right)-0\right]\times 2 = \ln\left(\frac{0.111}{1.889}\right)=-2.834
$$
The test statistics $= -2.834$

We can reject the null hypothesis

## Exercise 2
(See question on slide 14 on Blackboard)


Plugging these into normal equations
$$
\begin{array}{c}5\beta_1+599.2\beta_2=251.1\\ 599.1\beta_1+72304.24\beta_2=29951.72\end{array}
$$
Solving for $\beta_1,\beta_2$
$$
\beta_1=84.0633,\,\,\,\,\,\beta_2=-0.2824
$$
Our linear mode is therefore
$$
y=84.0633-0.2824x
$$
## Exercise 3
(See question on slide 18 on Blackboard)

$$
y=\beta_1\sin(2\pi t)+\beta_2\cos(2\pi t)
$$

Stating the error equation
$$
E=\sum_{i=1}^n (y-\beta_1s_i-\beta_2c_i)^2
$$
where $s_i=\sin(2\pi t_i),\, c_i=\cos(2\pi t_i)$

Deriving the normal equation by differentiating w.r.t $\beta_1$ and $\beta_2$
$$
\begin{array}{c}\frac{dE}{d\beta_1}=-2\sum_{i=1}^n s_i(y_i-\beta_1s_i-\beta_2c_i)=0\\[0.5em]\frac{dE}{d\beta_2}=-2\sum_{i=1}^n c_i(y_i-\beta_1 s_i-\beta_2c_1)=0\end{array}
$$
Normal Equations are therefore
$$
\begin{array}{c}\beta_1 n+\beta_2\sum_{i=1}^n x_i=\sum_{i=1}^n y_i\\ \beta_1\sum_{i=1}^n x_i+\beta_2\sum_{i=1}^n x_i^2=\sum_{i=1}^n x_iy_i\end{array}
$$

Calculating the required quantities 
$$
\begin{array}{c}\sum_{i=1}^n s_i^2=2.0721\\\sum_{i=1}^n s_ic_i=0.1715\\\sum_{i=1}^n c_i^2=2.9279\\\sum_{i=1}^n s_iy_i=1.1304\\\sum_{i=1}^n c_iy_i=3.4131\end{array}
$$

Putting these values into the normal equation gives us
$$
\beta_1=0.6451,\,\,\,\,\,\,\beta_2=1.2035
$$
