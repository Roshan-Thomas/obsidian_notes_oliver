---
title: Lecture 8
date: 16 Feb 2024
---
## Quick recap on hypothesis testing
Ideally we would like to be able to calculate $\underbrace{\Pr(\text{model | outcome})}_{\text{cannot calculate}}$

But we can only calculate $Pr\text{(outcome | model)}$

If the probability if small, then the implication is that the model is not true since the outcome did occur.

Bayes Theorem tells us that 
$$
P(M|O)=\frac{P(O|M)\times P(M)}{P(O)}
$$
The problem is that $P(O)$ is equal to 1 (since we have an observed outcome, therefore the probability of that outcome is 1).

$P(M)$ is the probability that the model is correct in the absence of any other information.
- This is something which we cant say with surety in any given situation.
- It lies in between 0 and 1 $([0,1])$

If $P(O|M)$ is small then $P(M|O)$ is also small. 
- If $P(O|M)$ is large, we cant say anything.

Note: It is possible that you can create a model that fits the data, but that model could be nonsense. For example, you could say that your model of the world is that a dice thrown always gives a 6, but based on your own personal experience, you know that is not true. So even if you get a 6 on the first throw of the dice which satisfies your model, the model created is wrong.


# Tails, errors and significance levels
- The right hand tail of a distribution is something we are interested in.
- Both ends of the spectrum are important, but in some graphs only a single tail is important.
	- For example: PSA cancer marker is a one-tailed test (right-tailed test)
The choice of a one-tailed or two-tailed testing depends on the problem - which variations matter?
- If you are being asked if this value is abnormally high, then its a one-tailed test.
- If you are asked if this is the norm, then its a two-tailed test.

One tailed test (right-tailed)
$$
p=\Pr(x\ge x)
$$
One tailed test (left-tailed)
$$
p=\Pr(X\le x)
$$
Two tailed test
$$
p=2\text{ min}(\Pr (X\ge x),\Pr(X\le x))
$$

We reject the null hypothesis of the p-value is below the significance level.
- There is a tradeoff in choosing a high or low significance value.

A false positive is telling a healthy person that they are sick.
A false negative is telling a sick person that they are healthy.

The number of false positives is the same as the rate of significance level.
- This is where the 5% number comes from where that is you acceptance of false positives.

False negatives are things we dont know much about. 

