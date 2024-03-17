---
title: Lecture 14
date: 15 Mar 2024
---
- One of the ways you can use $\chi^2$ test is to test if two variables are independent of each other.
## Example 1
(see question on Blackboard slides)

The null hypothesis
$$
H_o:\text{The data is distributed according to Poisson distribution.}
$$
We need a 2-tailed test at $5\%$ significance.
$$
\begin{array}{c|ccccc}\text{N misprints}&0&1&2&\ge 3&\text{Total}\\\hline \text{Observed}&63&28&8&1&100\\\hline P(x=k)&0.625&0.294&0.069&0.012&1\\\hline\text{Expected}&62.5&29.4&6.9&1.2\end{array}
$$
For a Poisson distribution we calculated the mean number of misprints
$$
\lambda=\frac{(0\times 63+1\times 28+2\times 8+3\times 1)}{100}=0.47
$$
Use it to calculate the probability of a given number of misprints using the formula 
$$
P(x=k)=e^{-\lambda}\frac{\lambda^k}{k!}
$$
Applying the formula,
$$
P(x=0)=e^{-0.47}\frac{0.47^0}{0!}=e^{-0.47}=0.625
$$
Our new categories
$$
\begin{array}{c|ccc}\text{N misprints}&0&1&\ge 2\\\hline\text{Observed}&63&28&9\\\hline \text{Expected}&62.5&29.4&8.1\end{array}
$$
So,
$$
\chi^2=\sum_{i=1}^n\frac{(O_i-E_i)^2}{E_i}=\frac{(63-62.5)^2}{62.5}+\frac{(28-29.4)^2}{29.4}+\frac{(9-8.1)^2}{8.1}=0.171
$$
The number of freedoms 
$$
\text{number of categories (3)}-1- \text{calculated values (1)}=1
$$
And, $\chi_1^2=5.024$. So, we cannot reject the null hypothesis.
## Example 2
(see question on Blackboard slides)

$$
P(\text{Green | Hit})=\frac{P(\text{Hit \& Green})}{P(\text{Hit})}=\frac{0.56}{0.572}=0.98
$$
