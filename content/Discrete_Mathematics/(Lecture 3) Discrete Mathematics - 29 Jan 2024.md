---
title: Lecture 3
date: 29 Jan 2024
---
# AT2: Automata Theory
## Non-deterministic Finite Automaton (NFA)
- A node where everything is going into it and nothing is going out is called a **Sink Node**.
	- Once you enter that node (Q2), you never leave.
- The NFA is not a DFA because there are two edges marked as 0 (two possible outputs)

The definition of a NFA is the same as for a DFA except that the transition function returns a set of states, rather than a particular state. 
	Formally we write this as $\delta:Q\times \sum\rightarrow 2^Q$, basically the power set of $Q$, the set of all subsets of $Q$.

- With an NFA, we need to calculate all the possible states that are reachable with an input string $w$.
	- The steps for an input string $w$ is:
		- we start on $q_0$
		- for each symbol in $w$, determine all possible states reachable from the current set of states.
		- when all symbols in $w$ have been used, $w$ is accepted if and only if at least one current state is final (accepting).

A simple automaton drawn strictly to cover all the cases of input strings.
![[Discrete_Mathematics/images/Pasted_image_20240129111353.png|500]]

The node $\phi$ represents the empty set, and is a place for all the inputs to go where it is not $010$.

#### **Example: NFA Transition table**

![[Discrete_Mathematics/images/Pasted_image_20240129111631.png|500]]
$$
\text{Transition table }\,\,\,\,\,\begin{array}{c|c|c}&0&1\\\hline q_0&\{q_1,q_2\}&\phi\\q_1&\phi&\{q_1\}\\q_2&\{q_3\}&\phi\\q_3&\phi&\phi\end{array}
$$
#### **Example: Regular Expressions**
The following machine accepts an expression we will denote as $01^{2n+1}0,\,\, n\ge 1$  
![[Discrete_Mathematics/images/Pasted_image_20240129112056.png|500]]

#### Example
$$
\text{Transition table }\,\,\,\,\begin{array}{c|c|c}&0&1\\\hline q_0&\{q_0,q_1\}&\{q_0\}\\q_1&\phi&\{q_2\}\\q_2&\{q_2\}&\{q_1\}\end{array}
$$

![[Discrete_Mathematics/images/Pasted_image_20240129112402.png|500]]

$$
(0|1)^*\, 0\, 1\, (0|1)^*
$$
**Note:** 
- | represents Alternatives
- $*$ means Repetition
- $()$ is used for Grouping

This Automator accepts any binary string containing a $01$.
- A regular expression is a term often used in text searches.

As long as one of the searches are accepted, then the NFA is accepted.

**Kleene closure** is all the strings that are coming out of it. All the repetitions that are coming out a particular search $A$. It is an infinite set as you can repeat it how many number of times you want to.
- $((a|b)a)^*=\{\epsilon, aa, ba, aaba, aaaa,baba,\dots\, aaaaaa\}$
- $(0|1)^*01(0|1)^*=\{01,00010,10110\dots\}$
- $(a|A)p^*(e|s|art)=\{as, Ape, Apps, apart,\dots\}$ 

### Observations
- Are NFAs more computational expensive?
	- No, it isn't because we can always convert a NFA into an equivalent DFA.
	- Equivalent means that the machines accept exactly the same strings.

### Example
Construct an NFA $\sum=\{0,1\}$ accepting strings that contain either $'01'$ or $'10'$

**DFA problems**
- we dont know how long the string is 
- we dont know where in the string are the $01$ or $10$.
- we also have the issue of $OR$.

Instead we can use a NFA, and draw it like this

![[Discrete_Mathematics/images/Pasted_image_20240129114527.png]]

### Example
Lets consider the NFA
![[Discrete_Mathematics/images/Pasted_image_20240129114856.png|500]]

$$
\begin{array}{c|c|c}&0&1\\\hline q_0&\{q_0\}&\{q_1,q_2\}\\q_1&\{q_1,q_2\}&\{q_2\}\\q_2&\{q_0,q_1\}&\{q_1\}\end{array}
$$
