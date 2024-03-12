---
title: Lecture 13
date: 12 Mar 2024
---
## Why are statistics important?
Statistics allow you to make sense of data. 
- It's important to get your statistical tests correct as it avoids false positives.

$\chi^2$ gives us a proper test that tells us if our sample follows the model. 

- Degrees of Freedom is how many categories your data can go in. 

## Exercise 1
The question is present in the slides for 12 Mar 2024 on Blackboard.

The null hypothesis
$$
H_o:\text{Random sample of 500 customers is the same as the model being given.}
$$

Performing a $\chi^2$ (chi-squared) test.
$$
\sum_{i=1}^n\frac{(O_i-E_i)^2}{E_i}
$$
$$
\begin{array}{c|ccccc|c}\text{Width}&A&B&C&D&E&\text{Total}\\\hline O&12&46&121&178&93&500\\ E&10&40&150&200&100&500\end{array}
$$

So,
$$
\begin{split}\chi^2&=\frac{(12-10)^2}{10}+\frac{(46-40)^2}{40}+\frac{(171-150)^2}{150}+\frac{(178-200)^2}{200}+\frac{(93-100)^2}{100}\\ &=\frac 4{10}+\frac{36}{40}+\frac{441}{150}+\frac{484}{200}+\frac{49}{100}\\&=7.15
\end{split}
$$
The degrees of freedom are 1-number of categories = 4 degrees of freedom

Using tables,
$$
\chi^2_4=9.488,
$$
$$
7.15<9.488
$$
Hence, we cannot reject the null hypothesis
# Independence Testing
- The degree of freedom is (rows-1)(columns-1) - data constraints

## Exercise 2
The question (50 people suffering from skin rash) is available on the slides for 12 Mar 2024 on Blackboard.

The null hypothesis
$$
H_o:\text{Both ointments are equally effective}
$$
We are going to treat both ointments as the same and derive a model which is a probability distribution 
$$
\begin{array}{c|c|c}&\text{Improved}&\text{Not Improved}\\\hline \text{Prob}&\frac{26}{50}=0.52&\frac{24}{50}=0.48\\\hline \text{Expected Usual}&30\cdot 0.52=15.6&30\cdot 0.48=14.4\\\text{Expected New}&20\cdot 0.52=10.4&20\cdot0.48=9.6\\\hline \text{Observed Usual}& 14&16\\\text{Observed New}&12&8\end{array}
$$
Calculating the $\chi^2$
$$
\begin{split}\chi^2&=\sum_{i=1}^n\frac{(O_i-E_i)^2}{E_i}\\&=\frac{(4-15.6)^2}{15.6}+\frac{(16-14.4)^2}{14.4}+\frac{(12-10.4)^2}{10.4}+\frac{(8-9.6)^2}{9.6}\\&=0.855\end{split}
$$
If we get a very small value of $\chi^2$, it is likely that the two ointments are the same.

The number of degrees of freedom is (rows-1)(columns-1) = $1$
$$
\chi^2_1=3.841\text{ at 10\% significance for a 2-tailed test}
$$
The value we calculated is smaller than $3.841$, so we cannot reject the null-hypothesis.
