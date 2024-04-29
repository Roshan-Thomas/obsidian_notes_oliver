---
title: Lecture 16
date: 29 Apr 2024
---
# Revision

![[Discrete_Mathematics/images/Pasted_image_20240429110835.png]]

**Part (a)**
Q - all the states
$\sum$ - alphabet
$\delta$ - transition function
$q_0$ - starting state
$F$ - set of final state

**Part (b) (i)** 
![[Discrete_Mathematics/images/Pasted_image_20240429111204.png]]

**Part (b) (ii)**
$$
\begin{array}{c|c|c}\delta_N&0&1\\\hline q_0&\{q_0,q_1\}&\{q_0,q_3\}\\ q_1&q_2&\phi\\ *q_2&\phi&\phi\\ q_3&\phi&q_2\end{array}\rightarrow \begin{array}{c|c|c}\delta&0&1\\\hline \{q_0,q_1\}&\{q_0,q_1,q_2\}&\{q_0,q_3\}\\\{q_0,q_3\}&\{q_0,q_1\}&\{q_0,q_2,q_3\}\\\star\{q_0,q_1,q_2\}&\{q_0,q_1,q_2\}&\{q_0,q_3\}\\\star\{q_0,q_2,q_3\}&\{q_0,q_1\}&\{q_0,q_2,q_3\}   \end{array}
$$
Drawing the DFA

![[Discrete_Mathematics/images/Pasted_image_20240429112106.png]]

**Part (c)**
$$
\begin{array}{c|c|c}\delta_N&0&1\\\hline \rightarrow q_0&q_0&q_1\\q_1&\{q_1,q_2\}&q_1\\\star q_2&q_2&\{q_1,q_2\}\end{array}\rightarrow \begin{array}{c|c|c}\delta&0&1\\\hline \rightarrow q_0&q_0&q_1\\q_1&\{q_1,q_2\}&q_1\\\star\{q_1,q_2\}&\{q_1,q_2\}&\{q_1,q_2\} \end{array}
$$
Sketching it,

![[Discrete_Mathematics/images/Pasted_image_20240429112728.png]]
___
![[Discrete_Mathematics/images/Pasted_image_20240429113147.png]]

**Part (a)**
This is no longer applicable as complexity has been removed from the syllabus for this year.

**Part (b)**
Proof by contradiction

Assume $H$ can decide whether an algorithm halts or loops forever.

![[Discrete_Mathematics/images/Pasted_image_20240429113450.png]]

Construct another machine $D$ which negates the input, if $H$ gives one then $D$ will loop forever, and stops if $H$ gives zero.

![[Discrete_Mathematics/images/Pasted_image_20240429113651.png]]

Consider if $D$ is given as an input to $H$. So if H gives one if $D$ halts, and zero if $D$ loops forever. 

![[Discrete_Mathematics/images/Pasted_image_20240429113951.png]]

This is not possible, as it contradicts it each other.

**Part (c) (i)**
The strategy is to read a bit and change it.

![[Discrete_Mathematics/images/Pasted_image_20240429114537.png]]

**Part (c) (ii)**
$$
\begin{array}{c}\text{State of even number of 1s}\\\text{State of odd number of 1s}\\\text{Decide at the end}\end{array}
$$
![[Discrete_Mathematics/images/Pasted_image_20240429114900.png]]
