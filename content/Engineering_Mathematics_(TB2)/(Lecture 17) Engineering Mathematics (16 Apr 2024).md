---
title: Lecture 17
date: 16 Apr 2024
---
# Applied Statistics
## Fallacies and bias
- Gambler's fallacy
	- Very common
	- Its the notion that over time if you take enough observations everything reverts to the mean. 
	- If the events are independent, then the probabilities won't change if it has happened before. 
- Correlation is not causation
	- Just because two variables are correlated doesn't mean that they have a causation.
- Base-rate fallacy (particularly for medical testing)
	- Just because a medical test has 99% accuracy, and you test positive for that disease does not mean that you have 99% probability of you ACTUALLY having the disease. The real probability is far lower.

If we have a 90% accurate test
$$
\begin{array}{|c|c|c|}\hline&\text{Test is +ve}&\text{Test is -ve}\\\hline \text{I have disease}&0.1\times 0.9=0.09&0.1\times0.1=0.01\\\hline \text{I don't have disease}&0.9\times 0.1=0.09&0.9\times0.9=0.81\\ \hline\end{array}
$$
The probability that you have the disease if you test positive is only 50-50 because both probabilities in the second column are equal.

- Survivorship bias
	- To avoid this bias you will need to split the population into two categories and then separate the models for each population.