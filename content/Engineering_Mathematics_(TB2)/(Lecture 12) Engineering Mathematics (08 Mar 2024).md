---
title: Lecture 12
date: 08 Mar 2024
---
# Resampling
This is the basis for most modern statistics, and is used a lot in industry. They are computationally heavy. 
### Conditions for difference of two sample means/paired t-test
- The conditions that are used are the same as the standard t-test.
- Observations are independent.
- Observations are normally distributed.

Resampling methods - underlying distribution is unknown.
- We say instead that the data that we have are the best representations of the distribution that we have.
- Asymptotic methods - work best in limit of large samples.
## Resampling - permutation test
Difference of two sample means
We have two different samples and look at the difference of the means 
$$
\text{A random distribution }\,\,\,\,\,\,\,\begin{array}{|c|c|}\hline A&B\\\hline 1.2&1.3\\1.7&1.5\\1.3&1.1\\1.9&1.0\\\hline \bar X_A&\bar X_B\\\hline\end{array}\,\,\,\,\,\, \bar X_A-\bar X_B
$$
$$
H_o:\text{ observations all come from the same poplulation}
$$
We can generate a new set of observations that is the old observations shuffled around (take some from sample A and some from sample B to get a new distribution)
$$
\begin{array}{|c|c|}\hline A&B\\\hline 1.2&1.3\\1.5&1.7\\1.3&1.1\\1.9&1.0\\\hline \bar X_A&\bar X_B\\\hline\end{array}\,\,\,\,\,\,\,\,\bar X_A-\bar X_B
$$
$$
\begin{array}{|c|c|}\hline A&B\\\hline 1.2&1.3\\1.7&1.5\\1.1&1.3\\1.0&1.9\\\hline \bar X_A&\bar X_B\\\hline\end{array}\,\,\,\,\,\,\,\bar X_A-\bar X_B
$$
Do this many many times and generate a histogram of all the possible combinations 

The distribution generated is called empirical distribution

And we understand the answer to the question of where the original difference in mean lies in the empirical distribution. 

We then understand where the critical values are (10% significance where the tails will have 5% of the data each). If the original distribution is in one of the tails of the empirical distribution we can reject the null hypothesis, but if its in the center then we can accept the null hypothesis.

## Resampling - bootstrap
In a standard t-test we only have a single sample such as $[1.3,1.1,1.7,1.2]$.

The bootstrap tells us that we can sample from the original data with replacement. 
$$
[1.3,1.1,1.3,1.7]
$$
And you can continue this process for many times, and calculate the mean for each of them. We then generate a histogram and work out where the original data set lies in the empirical distribution. If the original data set is in the tails of the empirical distribution, we can reject the null hypothesis, and if it's in the center of the empirical distribution we can accept the null hypothesis.

A nice thing about the bootstrap method is that it doesn't matter what statistic you actually use with the distribution.