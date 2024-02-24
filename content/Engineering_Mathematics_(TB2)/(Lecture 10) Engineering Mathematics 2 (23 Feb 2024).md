---
title: Lecture 10
date: 23 Feb 2024
---
# T tests
The key thing to whether to use a T-test or not is to work out what the null hypothesis actually is (mathematically).

### Previous Exam Question
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240224130946.png]]

No it's not a T-Test

The null hypothesis
$$
H_o:X\backsim N(0.22,0.06)
$$
assuming population is normally distributed
$$
\bar X\backsim N\left(0.22,\frac{0.06^2}5\right)
$$

- Population statistics are constants (fixed) and they are not random.
- Sample statistics are random variables, and they have their own distribution.
	- Sample mean follows the normal distribution (if the population is normally distributed).
	- Sample variance follows the $\chi^2$ (chi-squared) distribution.

The Z-score
$$
Z=\frac{\bar x-\mu}{\frac\sigma{\sqrt n}}=\frac{0.174-0.22}{0.06/\sqrt 5}=-1.71
$$
This is two-tailed test with 10% significance
$$
Z_{int}=[-1.645,+1.645]
$$
So, we can reject the null hypothesis.

### Example
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240224131736.png]]

The null hypothesis (Normality is assumed)
$$
H_o:X\backsim N(25,?)
$$
We have to use the T-distribution as it allows us to estimate the variance from the sample,
$$
\bar X\backsim T(25, \frac{s^2}{n})
$$
This is a one-tail test as the lorries don't care if they are under-loaded (they are saving fuel costs), and the significance level is 5%
$$
\bar X=27.54
$$

The sample variance (always $n-1$)
$$
s^2=\frac{1}{n-1}\sum_i(X_i-\bar X)^2=29.93
$$
So, the T-score
$$
\begin{split}T&=\frac{\bar X-\mu}{S/\sqrt n}\\&=\frac{27.54-25}{\sqrt{\frac{29.93}5}}\\&=1.04\end{split}
$$
$$
T_{cit}=2.132
$$
Therefore, cannot reject $H_o$ as there is not enough evidence to show that that haulage company is being misled.

### Example
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240224133347.png]]

$$
\bar X=4.67
$$
$$
s^2=124.42
$$
The null hypothesis
$$
H_o:X\backsim N(0,?)\,\,\,\,\,\,\text{assuming normality}
$$
$$
\bar X\backsim T_{11}\left(0,\frac{124.42}{12}\right)
$$
with 5% significance, and it is a one-tailed test

The T-score
$$
T=\frac{4.67}{\sqrt{\frac{124.42}{12}}}=1.45
$$

$$
T_{cnt}=1.796
$$
## When to use a T-Test?

Do we have a population variance?
- If yes, then we use Z-score (normal distribution)
- If no, then we use T-score (T-distribution)
- No but n is large, then use Z-score because for large n, the normal distribution proportional to T
	- You don't need to use this approximation.





