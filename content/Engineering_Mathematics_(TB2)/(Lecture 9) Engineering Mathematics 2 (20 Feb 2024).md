---
title: Lecture 9
date: 20 Feb 2024
---
# Applied Statistics
Let's look at the example we looked at, the one with the prostate cancer, and we had two cases, the healthy case, and the sick case. 

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240221095312.png|400]]

The healthy is my null-hypothesis. 

And as discussed last week, this is not a good test because there is no way to draw a line accurately that divides the two distribution without problems.

A statistical test that we can do in engineering is the possibility of collecting more data, unlike the medical field. And you can end up with two distributions that are separate, which are the null and alternative distributions.

Here $H_A$ is the alternative distribution and $H_o$ is the null-hypothesis, and $C_l$ stands for the clear space between the two distributions. The more of the data we get, the narrower the distribution. 

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240221095503.png|400]]

We can create a trade-off, 
1. Errors - false positives and false negatives.
2. Sensitivity of the experiment.
	- It tells what is the smallest change that can be detected in the experiment. In some scenarios, you want to detect the smallest changes. For example: finance, where 1% makes a lot of difference in money.
3. Amount of data collected.

## Example: Bag of flour
(The statement of the problem is given on Blackboard).

The first thing to note is the change we need, which is 10g and the errors we are happy to accept 5% and 20%.

The null distribution is the distribution centered at 1050g

The alternative distribution is of 10g, and is the distribution centered at 1060g.

The dividing line should be drawn in such a way that the false positives are 5% and the false negatives are 20%

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240221100420.png|500]]

The standard deviation of the machine itself is 20g.

The sample mean is normally distributed 
$$
H_o:\bar X\backsim N\left(1050,\frac{20^2}n\right)
$$
The alternative hypothesis is normally distributed
$$
H_A:\bar X\backsim N\left(1060,\frac{20^2}{n}\right)
$$
False positives are defined as,
$$
P(X\ge X_c|H_o)=0.05
$$
where $X_c$ is the critical value, which decides the dividing line.

False negatives are defined as,
$$
P(X\le X_c|H_A)=0.20
$$

The first thing we are going to do is convert the false negatives into a standard normal distribution. The standard normal distribution is the normal distribution with a width of 1.

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240221101002.png|400]]

$$
P(X\le X_c|H_A)=P\left(Z\le \frac{X_c-1060}{20/\sqrt{n}}\right)=0.2
$$
From the statistical tables
$$
\Rightarrow \frac{X_c-1060}{20/\sqrt n}\le -0.8416
$$

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240221102007.png|400]]

With a significance level of 5%, the critical value can be written as the mean of my null hypothesis
$$
X_c=1050+1.645\times \frac{20}{\sqrt n}
$$
$$
\frac{1050+1.645\times 20/\sqrt n-1060}{20/\sqrt n}\le-0.8416
$$
By rearranging,
$$
\Rightarrow 1.645-\frac{10}{20/\sqrt n}\le -0.8416
$$
$$
\Rightarrow \frac{10}{20/\sqrt n}\ge 2.486
$$
$$
\Rightarrow \sqrt n\ge 4.973\,\,\,\,\,\,\Rightarrow n\ge 24.7
$$
This gives us the number of observations that we need. So we need a minimum of 25 observations to achieve the required errors, for 10g of sensitivity.

## Example: Aluminum Alloys

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240221102417.png|500]]
