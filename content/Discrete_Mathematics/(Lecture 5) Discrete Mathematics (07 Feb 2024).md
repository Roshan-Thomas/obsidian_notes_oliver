---
title: Lecture 5
date: 07 Feb 2024
---
# Turing Machines (TM)
- DFAs have limitations, and there are certain things they cant recognize such as $0^n1^n$.
- DFAs can check arithmetic, but they can't calculate.
- The reason for the limitations of DFA is cause of the number of nodes.

- To handle these shortcomings, a Turning machine is made which is essentially a DFA with a memory store.
	- The memory is an infinite tape cut into sections in which you can store information in each section. You are allowed to write to memory, overwrite, and move around in the memory.

- We have a reader head, and we move along the tape (a reader that reads each section), and while looking at a particular section, we can only see that section and nothing else.
$$
\text{Memory in a Turning Machine} \,\,\,\,\,\begin{array}{|c|c|c|c|c|c|c|c|}\hline S&1&1&0&B&B&B&\\\hline\end{array}
$$
$$
\text{ B represents Blank, S represents Start}
$$

A TM is a 6-tuple
- $Q$ is a set of finite states
- $\sum$ is a set of symbols (input alphabet)
- $q_0$ is our starting state.
- $F$ is a finite set of accepting states
- $\delta$ is the transition function $Q\times\Gamma\rightarrow Q\times\Gamma\times\{L,R\}$
- $\Gamma$ is a set of symbols (tape alphabet) $\Gamma>\sum$

Thats all we need to have a Turing machine.

- A Turing machine halts when it 
	- reaches a final state (computation succeeded)
	- or if the process has failed

### Example of a Turing Machine
Device a TM to invert a binary string (this is called one's complement). In this case:
$$
\sum=\{0,1\}\,\,\,\,\,\,\Gamma=\sum\cup\{S,B\}
$$
with $q_1$ as the final state

![[Discrete_Mathematics/images/Pasted_image_20240207103804.png|500]]

# A second example
Consider an even parity tester i.e. the TM reads an input string and places a 1 on the tape in the first position with following blank, if the input string was an even number, or 0 with following blank if odd. The is TM is as follows:

![[Discrete_Mathematics/images/Pasted_image_20240207104352.png]]

The number 6 in binary
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&1&1&0&E&B\\\hline\end{array}
$$
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&\boxed{1}_{q_0}&1&0&E&B\\\hline\end{array}
$$
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&1&\boxed{1}_{q_0}&0&E&B\\\hline\end{array}
$$
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&1&1&\boxed{0}_{q_0}&E&B\\\hline\end{array}
$$
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&1&1&0&\boxed{E}_{q_1}&B\\\hline\end{array}
$$
Once we reach a blank, we go to
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&1&1&\boxed{0}_{q_6}&E&B\\\hline\end{array}
$$
After this, we go all the way back to the start, and then
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&\boxed{1}_{q_7}&1&0&E&B\\\hline\end{array}
$$
$$
\begin{array}{|c|c|c|c|c|c|}\hline S&1&\boxed{E}&0&E&B\\\hline\end{array}
$$
This tells us that the given number is even.