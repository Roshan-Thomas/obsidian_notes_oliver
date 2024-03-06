---
title: Lecture 11
date: 05 Mar 2024
---
# Applied Statistics: More t-tests

### Example

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240306214419.png]]

The key question is what type of t-test to do here.
There is a link between the groups of people, as the IQs of the father's and mother's combine for the child. So it's likely to have a correlation between the two samples. And we have to use the $\Delta$ column for testing.

So, this is a *paired t-test*.

We start with our null hypothesis
$$
\begin{array}{c}H_o:\text{ both samples are drawn from the same population}\\\implies \text{both samples have the same mean}\end{array}
$$

This is a two-tailed test and 5% significance.

Using the standard T-test statistic
$$
T=\frac{\bar x-\mu}{s/\sqrt{n}}=\frac{3.4}{74/\sqrt{36}}=2.72
$$
$$
T_{35}(0.05)=2.04
$$
Therefore, we are rejecting the null hypothesis, and there is a difference in the IQs of the two samples.

## Example

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240306215925.png]]

This is a sample means test, as there is no-links between the two groups. 

The null hypothesis
$$
\begin{array}{c}H_o:\text{both samples are drawn from the same population}\\\implies \text{their means are the same.}\end{array}
$$
We have 5% significance, and we have a two-tailed test.
$$
T=\frac{x_1-x_2}{\sqrt{\frac{s_1^2}{n_1}+\frac{s_2^2}{n_2}}}=\frac{98.105-98.394}{\sqrt{\frac{0.699^2}{65}+\frac{0.743^2}{65}}}=-2.276
$$
The number of degrees of freedom 
We use the minimum (n) as our numbers of degrees of freedom
$$
\text{numbers of degrees of freedom}=\min(n_1,n_2)=65-1=64
$$

$$
T_{64}(0.05)\approx 2.000 \,\,(=1.998)
$$
So, we reject $H_o$ and there is a difference in body temperatures.

We have shown that there is a statistical difference between the two groups. But it doesn't have a practical significance.

## Multiple hypotheses and Bonferroni correction
What happens when you have multiple hypotheses you want to test?

Often what happens is you generate a hypothesis, then develop an experiment to test the hypothesis, and it won't work. Then create a new hypothesis and the process repeats.

When we have multiple hypothesis on the same data, that presents a problem of false positives or Type 1 errors.

A simple way around this is the **Bonferroni correction**, which says if you have a hypothesis of 5% significance then you should use a significance level of $5\%/n$.  