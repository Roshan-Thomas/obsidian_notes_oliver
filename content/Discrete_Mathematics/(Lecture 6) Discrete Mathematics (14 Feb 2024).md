---
title: Lecture 6
date: 14 Feb 2024
---
- We can replace common paths such as the MoveToTapeStart path as a block and name it MoveToTapeStart.
### Successor function
In binary arithmetic, the successor function is $f(n)=n+1$, where the read input string is $n$ and $n+1$ is left on the tape.
$$
f(101)=110\,\,\,\,\, f(110)=111\,\,\,\, f(111)=1000
$$
In binary
$$
\begin{array}{cccc}1&0&1&\\&&1&+\\\hline 1&1&0\end{array}\,\,\,\,\,\,\,\,\,\,\begin{array}{ccccc}&1&1&1&\\&&&1&+\\\hline 1&0&0&0\end{array}
$$
If we have a string,
$$
S\,1\,1\,1
$$
We have three rules
- If we have a 1 then overwrite 0 and go left (carrying the 1).
- If we have a 0, then overwrite 1 and we stop
- If we have a S (start) then we have to shift the entire string down because we need to make space for the 1 that we are carrying.
	- Move right, overwrite 1 and then go to the end and over $E$ with a zero.
$$
S\,1\,1\,1\Rightarrow S\,1\,\overbrace{0\,0\,0}^{\text{shifted}}
$$

# Multiple inputs
- we introduce a new symbol on the Turing machine known as $\#$ which means that we have can multiple inputs in the Turing machine.

We can do addition with two inputs $w1$ and $w2$ using a Turing Machine using the algorithm:
1. Is $w1$ a zero string?
2. If yes, then the answer is in $w2$
3. If no, then increment $w2$, decrement $w1$ and then go back to step 1

By manipulating the steps above we can make a calculator (addition, subtraction, multiplication, and division).
## Composition of Turing machines
- we can do complex tasks of function composition with a Turing machine

We have seen before that DFAs can't do calculations, but Turing machines can, but we need to ask what is computable? 

# What can Turing machines do?
- Evaluate functions
- Implementing decision problems
- Accept or reject language strings
- It can processes a language string such as copy a word with a $\#$ separator

In performing tasks:
- Computation steps from taking a single composition to another configuration.
- A computation is a sequence of such steps

An important feature is that if the start configuration does not lead to an accepting state or a rejecting configuration, then the Turing Machine loops (does not halt), which is a major problem.

**Computability** refers to the question of whether or not it is possible to effectively evaluate a function.
- A Turing machine embodies an effective procedure.
- We say that something is Turing computable if you can use a Turing Machine to compute it.

# Church-Turing Thesis
> **Any effective procedure can be encoded as a Turing Machine**

- This is a Thesis and not a theorem cause it hasn't been proved yet.
# Extended Turing Machines
Its possible to extend the standard Turing Machines by:
- allowing the tape to extend infinitely in both directions
- allow multiple tapes (with independent read/write heads)
- allow a non-deterministic automaton.


It can be shown that all such extensions are equivalent to the standard Turing Machines
## Turing machines as strings
- we can encode a TM as a string themselves

We can represent a transition table as a string using the convention
$$
<\text{initial state, input, output, move, new state}>
$$
- There are functions for which no effective calculating procedure exists.

This mirrors the incompleteness theorems, which states that for a given set of axioms there are some true statements that doesn't have axioms.
# Universal Turing Machines (UTM)
We can put the output of a Turing machine and an input string and we can put it into another Turing Machine.
- It can have three outcomes of accept, reject, and looping indefinitely.

We can also have a Turing machine where each block contains an encoded string of another Turing Machine.

- A UTM reads such an encoding of a Turing Machine and its encoded state.
- A UTM need not be that large.

Now, we come to the Halting problem, where can we determine whether a given Turing machine halts on a given input $w$.
# Halting Problem
Lets assume that we can build a machine that can detect infinite loops

*(Image can be found on Slide 25 of Turing Machines 2 Slides)*

We have an $enc(TM)\#w$ which goes into the halt checker $H$, and it gives a 1 if $TM$ halts on $w$, or gives a 0 if $TM$ loops on $w$.

We can inverse this and say that if we get a 1 then we loop forever, and if TM loops we still output 0.

We can add a copier Turing machine which copies $enc(TM)$ to $enc(TM)\# enc(TM)$ and then it goes into our halt checker $H$.
- If this entire system is labelled as $D$, then we get a TM which is encoded as a string, which acts as an input. 
- So if we input $D$ into $D$, then 
	- D will loop if D halts
	- D will halt if D loops

By a proof of contradiction it is shown that the Halting problem cannot be be solved or we can't make a machine that checks if a system loops forever.
