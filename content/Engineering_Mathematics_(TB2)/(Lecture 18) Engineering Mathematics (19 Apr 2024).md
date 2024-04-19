---
title: Lecture 18
date: 19 Apr 2024
---
## Principles of experiment design
- Controls
	- Determine the potential factors that can cause variation and design the experiment to minimize them
- Randomization
	- Anything you can't control, you will want to randomize it to minimize bias
- Replication
	- Make as many observations as possible
- Blocking
	- If there are factors that are going to affect your experiment and can't control them, then do the experiment and divide the sets into blocks based on the factors.
## Example
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240419151047.png]]

- One of the factors that affects migraines is stress, and we can use that as a factor in our blocking. Stress is easy for recording, and can easily be used as a factor in our observation.
- We can control for the dosage of the drug used on the patient or test subject.
- We can randomize the age of the test subjects, as we don't want bias with the age of a particular test group.

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240419151722.png]] 

Out of the below options, which one is the best choice,
a) The Z-score
b) T-score
c) Paired T-test
d) Difference of sample means
e) Goodness-of-fit $\chi^2$ test
f) Independence $\chi^2$
g) Expected value
h) Correlation Test

The answer is the **Paired T-test**, because the same patient has a before and after test.

N.B. Based on the data and the format of it should influence what type of test you use. 

## Example
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240419152835.png]]
This is a **paired-T test**, because the data that is being measured shows the before (old shift pattern) and after (new shift pattern).

The assumptions that you making about the data are,
- independence
- assumption of normality (unless you have a lot of data 100+)

## Example
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240419153536.png]]

This is an **Independence $\chi^2$ test**. The data that is being measured is what club the winner goes to and their age.

N.B. Make sure you know what is being *observed*!
