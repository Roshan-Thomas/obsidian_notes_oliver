---
title: Lecture 2
date: 24 Jan 2024
---
# Equivalent DFAs
Both DFAs do the same task or are equivalent if they share the same language $L(M)$.
- For any regular language, there is a unique DFA with a minimum number of states

# Designing a DFA
To design a DFA for a given task, we have to have information detailing 
- the set of states $Q$
- the alphabet $\sum$
- the start state $q_0$
- the final or accepting state $F$
- The transition function $\delta$

Consider an example where
- $Q=\{a,b,c\}$
- $\sum=\{0,1\}$
- $q_0=\{a\}$
- $F=\{c\}$

The transition function in the form of a table
$$
\begin{array}{c|c|c}\text{Present State}&\text{Next State for input 0}&\text{Next state for input 1}\\\hline a&a&b\\b&c&a\\c&b&c\end{array}
$$
The state diagram would be

![[Discrete_Mathematics/images/Pasted_image_20240203165956.png|250]]

## Example 1
Design a DFA given a 5-tuple $D=(\{q_1,q_2\},\{a,b\},\delta,q_1,\{q_2\})$ and $\delta$ is given by
$$
\begin{array}{c}\delta(q_1,a)=q_1\,\,\,\,\, \delta(q_2,a)=q_1\\ \delta(q_1,b)=q_2\,\,\,\,\, \delta(q_2,b)=q_2\end{array}
$$
Determine the language $L(D)$ of the DFA

$Q=\{q_1,q_2\}$
$\sum=\{a,b\}$
$q_0=\{q_1\}$
$F=\{q_2\}$

$$
\text{Transition Table }\,\,\,\,\,\,\begin{array}{c|c|c}\delta&a&b\\\hline q_1&q_1&q_2\\q_2^*&q_1&q_2^*\end{array}
$$

![[Discrete_Mathematics/images/Pasted_image_20240203172828.png|300]]

## Example 2
Design a DFA for the language $L$ such that it accepts all strings in the alphabet $\sum=\{0,1\}$ that contain at least one $0$.

$Q=\{q_0,q_1\}$
$\sum=\{0,1\}$
$q_0=q_0$
$F=q_1$

$$
\text{Transition Table }\,\,\,\,\begin{array}{c|c|c}\delta&0&1\\\hline q_0&q_1^*&q_0\\ q_1^*&q_1^*&q_1^* \end{array}
$$

The State diagram

![[Discrete_Mathematics/images/Pasted_image_20240203173333.png|300]]

## Example 3
Design a DFA for a language $L$ in which strings with an odd number of $b's$ are accepted with any number of $a's$

$Q=
$\sum=\{a,b\}$
$q_0=q_0$
$F=q_1$

![[Discrete_Mathematics/images/Pasted_image_20240203174359.png|300]]

Accepted Strings are $b, bbb, bbbbb, \dots$
Unaccepted strings are $\phi,bb,bbbb,\dots$

$$
\text{Transition Table }\,\,\,\, \begin{array}{c|c|c}\delta&a&b\\\hline q_0&q_0&q_1^*\\q_1^*&q_1^*&q_0\end{array}
$$
## Example 4
Design a DFA to accept all string on $\{a,b\}$ such that the string must contain an even number of $a's$ and an even number of $b's$.

$L(N)=\{w|w\text{ contains an even number of a's and even number of b's}\}$

$Q=\{q_0,q_1,q_2,q_3\}$
$\sum=\{a,b\}$
$q_0=q_0$
$F=q_0$

Note: The empty string is even, if not explicitly written.

Accepted Strings are $\phi,aa,bb,aabb,abab\dots$
Unaccepted Strings are $b,\dots$

![[Discrete_Mathematics/images/Pasted_image_20240203181046.png|300]]

$$
\text{Transition Table }\,\,\,\,\begin{array}{c|c|c}\delta&a&b\\\hline q_0^*&q_1&q_2\\ q_1&q_0^*&q_3\\q_2&w_2&q_0^*\\q_3&q_2&q_1\end{array}
$$

$$
N=\{\{q_0,q_1,q_2,q_3\},\{a,b\},\delta,\{q_0\},\{q_0\}\}
$$
