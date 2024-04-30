---
title: Lecture 21
date: 30 Apr 2024
---
# Revision
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240430150425.png]]

First thing you have to do is to find out what is being measured in the question.

We are working on numerical data, so that means a Z-score or T-test (regular, paired, or two-sample means).

Next we have to find is how many samples are there, and there are 2 samples. So that means it's going to be either a Paired T-test or Two-sample means T-test.

The next thing we have to find is whether they are independent or dependent. From the data, it looks like it is independent. 

The null hypothesis
$$
H_0:\text{ means of two samples are the same}
$$
Two-tailed test, at 5% significance
$$
T=\frac{\bar X_1-\bar X_2}{\sqrt{\frac{S_1^2}{n_1}+\frac{S_2^2}{n_2}}}=\frac{65.2-74.9}{\sqrt{\frac{449.8}5+\frac{296.0}{5}}}=-0.795
$$
$$
T_{\text{critical}}=\pm 2.776
$$
The computed value is within the bounds, therefore you cannot reject the null hypothesis $H_0$

The assumptions are
- Independence of observations (within a sample)
- Approximately normally distributed

The potential issues could be
- the data is not normal
- spending within each sample is not independent
____
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240430152535.png]]

With 500 people, the Central limit theorem (CLT) applies.

The different test you can apply are:
- Z-score test - difference of means
- Resampling - difference of means
- $\chi^2$ - goodness of fit
	- low/medium/high blood pressure
	- This test tells us about the shape of the distribution
___
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240430153618.png]]

The key thing with linear regression is that it is not linear in the shape of the function, rather it is linear with the parameters that you are trying to fit. 

A quadratic function would fit this data much better.
$$
y=\beta_0+\beta_1 x+\beta_2 x^2
$$
This is a non-linear function, but it is a linear regression problem because each of these parameters appears as a linear combination.

For the data to have a linear regression, the data must be
1. Homoscedastic: constant variance 
2. Residuals are normally distributed

**Part (b)**
$$
||e||^2=\sum_i (y_i-\beta_0-\beta_1 x_i-\beta_2 x_i^2)^2
$$
$$
\frac{d||e||^2}{d\beta_0}=-2\sum_i(y_i-\beta_0-\beta_1 x_i-\beta_2 x_i^2)=0
$$
$$
\implies n\beta_0+\beta_1\sum_i x_i+\beta_2\sum_i x_i^2=\sum_i y_i
$$
$$
\frac{d||e||^2}{d\beta_1} \implies \beta_0\sum_i x_i+\beta_1\sum_i x_i^2+\beta_2\sum_i x_i^3=\sum_i x_iy_i
$$
You can repeat the same differentiation step for  $\beta_2$
The numbers can be calculated from the data, and you will end up with three linear equations which you can solve.
