---
title: Lecture 7
date: 13 Feb 2024
---
# Introduction to Applied Statistics
### Why statistics?
Engineers need a good appreciation of statistics as 
- High performance engineering requires smaller and smaller error margins
- Uncertainty quantification is a hot topic for aerospace and nuclear.
- Products, machines and people are complicated to model.
- There is a lot of data to comprehend.

Statistics is about thinking about the details and understanding them.

Textbooks:
- OpenIntro Statistics (4th Edition)
- Introduction to Modern Statistics (1st Edition)

Statistics is about modelling the real world - no right answers
____
# Introduction to hypothesis testing
### Prior Beliefs
- Whenever we use hypothesis testing, we require a prior belief about the world.
	- And then try to demonstrate that this belief is wrong.

- Some Common null hypothesis are
	- Innocent until proven guilty
	- No change - a new drug treatment is no different to the old drug treatment
### Framing the Problem
- We have to start with a model of the world
- We have observations from the world
- And, we want to know how well the observations fit with the model.
### A statistical model
- all models are wrong, but some are useful
	- A statistical model is a mathematical representation of the world
	- It generates data in the same form as our observations

A simple model for purely random jury selection
$$
X\backsim \text{Bin}(12,0.25)
$$
where $X$ is the number of African Americans selected for the jury, 12 is the number of jurors or number of observations, and 0.25 is the probability of selecting African American.

- This is all done assuming the process is fair.

#### Calculation of Engineers selected
Null hypothesis: selection is random
$$
X\backsim \text{Bin }(10,0.1)
$$
- This doesn't work exactly because all the cases are not independent of each other, and the statistical measurements is not the correct approach.
- **Critical thinking is key in statistics**
