---
title: Lecture 4
date: 31 Jan 2024
---
# Automata Theory

## Finding a DFA equivalent to a NFA

#### Example
Consider the regular expression $(0|1)^*01$ which accepts any binary string ending in $01$. This is implemented using the NFA:

![[Discrete_Mathematics/images/Pasted_image_20240131100650.png]]

The transition table 
$$
\text{Non-deterministic transition table }\delta_N\,\,\,\,\,\,\begin{array}{c|c|c}\delta_N&0&1\\\hline q_0&\{q_0,q_1\}&\{q_0\}\\ q_1&\phi&\{q_2\}\\q_2&\phi&\phi\end{array}
$$
To find the equivalent DFA, we list the power set of all states in the NFA.
$$
\begin{array}{c|c|c}\delta_D&0&1\\\hline \phi&\phi&\phi\\q_0&\{q_0,q_1\}&\{q_0\}\\q_1&\phi&\{q_2\}\\q_2\,\,\,\, *&\phi&\phi\\\{q_0,q_1\}&\{q_0,q_1\}&\{q_0,q_2\}\\\{q_0,q_2\}\,\,\, *&\{q_0,q_1\}&\{q_0\}\\\{q_1,q_2\}\,\,\, *&\phi\,\cup\,\phi=\phi& \{q_2\}\\\{q_0,q_1,q_2\}\,\,\, *&\{q_0,q_1\}&\{q_0,q_2\}\end{array}
$$
Note: $*$ represents an accepting state (contains $q_2$)

We realise that some of these states are not reachable from the start $\{q_0\}$
Row 2
$$
0\mapsto R5\,\,\,\,\,\text{ OR }\,\,\,\,\,1\mapsto R2
$$
Row 5
$$
0\mapsto R5\,\,\,\,\,\text{ OR }\,\,\,\,\,1\mapsto R6\,\, \{q_0,q_2\}
$$
Row 6
$$
0\mapsto R5\,\,\,\,\,\text{ OR }\,\,\,\,\,1\mapsto R2\,\,\{q_0\}
$$

So we can ignore all the states that are not reachable from $\{q_0\}$ 
$$
\begin{array}{c|c|c}\delta_D&0&1\\\hline \{q_0\}&\{q_0,q_1\}&\{q_0\}\\\{q_0,q_1\}&\{q_0,q_1\}&\{q_0,q_2\}\\\{q_0,q_2\}&\{q_0,q_1\}&\{q_0\}\end{array}
$$

The transition diagram for the equivalent DFA is then:

![[Discrete_Mathematics/images/Pasted_image_20240131102850.png|600]]

#### Example 2
Convert the following NFA to a DFA
![[Discrete_Mathematics/images/Pasted_image_20240131103234.png|500]]

The transition table:
$$
\begin{array}{c|c|c}\delta_N&0&1\\\hline q_0&\{q_1,q_2\}&\phi\\q_1\,\,\, *&\phi&\phi\\q_2&\{q_1,q_2\}&\{q_2\}\end{array}
$$
The set of states that we can reach $Q'$,
$$
Q'=\{q_0,\{q_1,q_2\}\}
$$
$$
\begin{array}{c|c|c}\delta_D&0&1\\\hline q_0&\{q_1,q_2\}&\phi\end{array}
$$
New state added,
$$
\begin{array}{c}\delta_D\left(\{q_1,q_2\},0\right)=\delta_N(q_1,0)\,\cup\, \delta_N(q_2,0)=\phi\,\cup\,\{q_1,q_2\}=\{q_1,q_2\}\\ \delta_D\left(\{q_1,q_2\},1\right)=\delta_N(q_1,1)\,\cup\,\delta_N(q_2,q)=\phi\,\cup\,\{q_2\}=\{q_2\}\end{array}
$$
So the updated $Q'$
$$
Q'=\{q_0,\{q_1,q_2\},q_2\}
$$
So,
$$
\begin{array}{c}\delta_D(q_2,0)=\delta_N(q_2,0)=\{q_1,q_2\}\\ \delta_D(q_2,1)=\delta_N(q_2,1)=\{q_2\}\end{array}
$$
$$
\begin{array}{c|c|c}\delta_D&0&1\\\hline q_0&\{q_1,q_2\}&\phi\\ \{q_1,q_2\}&\{q_1,q_2\}& \{q_2\}\\q_2&\{q_1,q_2\}&\{q_2\}\\ \phi&\phi&\phi\end{array}
$$
The transition diagram of the resultant DFA

![[Discrete_Mathematics/images/Pasted_image_20240131104216.png|500]]

#### Example 4
Consider the NFA below, find the equivalent DFA

![[Discrete_Mathematics/images/Pasted_image_20240131104529.png|500]]

$$
\begin{array}{c|c|c}\delta_N&0&1\\\hline q_0&q_0&\{q_1,q_2\}\\ q_1&\{q_1,q_2\}&q_2\\ q_2\,\,\, *&\{q_0,q_1\}&q_1\end{array}
$$

$$
\begin{array}{c|c|c}\delta_D&0&1\\\hline q_0&q_0&\{q_1,q_2\}\\ \{q_1,q_2\}&\{q_1,q_2,q_0\}\equiv \{q_0,q_1,q_2\}&\{q_1,q_2\}\\ \{q_0,q_1,q_2\}\,\,\, *&\{q_0,q_1,q_2\}& \{q_1,q_2\}\end{array}
$$

Plotting it

![[Discrete_Mathematics/images/Pasted_image_20240131105110.png|500]]

We can shorten it,

![[Discrete_Mathematics/images/Pasted_image_20240131105202.png]]

The regular expression would be
$$
0^*1(011)^*
$$