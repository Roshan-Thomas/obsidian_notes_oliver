---
title: Lecture 1
date: 22 Jan 2024
---
Discrete maths is about computation. 

Four major pieces of this course:
- Automata Theory
- Turning Machines
- Algebraic Structures
- Game Theory

# Automata Theory
An automaton is a machine that automatically follows a sequence of instructions.

- Automata theory tells us the limitations within computation.
- Finite Automaton has no memory

- A turning machine is capable of universal computation.
- Computability: Some solutions cant be effectively computed
- Halting Problem: An algorithm that a given input will terminate.
	- This is why modern algorithms have the problem of infinite loops.

A simple diagram of an automaton. The circles are the states, and the arrows represent the direction of travel if we get a true statement for the state.

![[Discrete_Mathematics/images/Pasted_image_20240203144639.png]]

## Finite Automaton
- Finite Automaton: A simple computational process with a limited range of inputs and states.
- Has a finite or limited set of states.
- **Deterministic Finite Automaton (DFA)**
	- It works the same every time, and there is no choice involved.

Examples
- $Q$ is finite set of states
- $\sum$ is finite set of symbols (alphabets)
- $\delta:Q\times\sum\rightarrow Q$ is a transition function
- $q_0$ is start state
- $F$ is a set of final states (accepting states)

## Strings
- DFA are used for lexical analysis i.e. processing strings, and for finding patterns.
- A regular expression (regex) is an example of automaton.
- A string over an alphabet, $\sum$ is a sequence of concatenated symbols from the alphabets.
- An entire set of such strings is $\sum^*$

$$
\Sigma^*=(\phi,0,1,01,10,00,11,000,001,\dots)
$$
## Language
A language $L$ is a subset of strings over an alphabet, or
$$
L\subset \Sigma^*
$$
We follow the convention that $a,b,c,\dots$ are symbols and $u,x,w,x,\dots$ are strings.

## DFA
Consider a DFA for recognizing binary strings containing 01
- $01,001,101,110011,\dots$ are accepted
- $1,11,10,100,\dots$ are NOT accepted as it doesn't contain $01$.

#### Example 1
The state graph for the automaton for doing this is

![[Discrete_Mathematics/images/Pasted_image_20240203150018.png]]

- we need to always end in an accepting state
$$
Q:\{q_0,q_1,q_2\}
$$
$$
\sum:\{0,1\}
$$
$$
q_0:\{q_0\}
$$
$$
F:\{q_2\}
$$
- The start state is indicated by a source less edge (open arrow).
- The accepting state is indicated by double circle (or bold)
- Edges are labelled by symbols from the alphabet.
- A string is recognised i.e. accepted, if the DFA reaches an accepting/final state.

### Example 2
Consider the transmission of 7-bit characters
$$
1000001, 1100001, 1100010,\dots
$$
Sender transmits 7-bits, and a parity bit of $0$ or $1$, with $0$ for even parity and $1$ for odd parity.

If the receiver gets an odd number of 1s then a transmission error is indicated.

The state graph is

![[Discrete_Mathematics/images/Pasted_image_20240203151008.png]]

The *execution trace* is to actually trace through the numbers through the system.

## The DFA Transition Function
The transition function $\delta$ is written as
$$
\delta(\overbrace{q}^{\text{state}},\overbrace{a}^{\text{input}})=\underbrace{q'}_{\text{new state}}
$$
### Strings
We define it so 
$$
\delta(q,\epsilon)=q'
$$
$$
\delta(q,\epsilon)=q
$$
$$
\delta(q,aw)=\delta(q',w)
$$
where $\delta(q,a)=q'$ and $q,q'\in Q,\, a\in \sum,$ and $w\in\sum'$

The empty set would mean no movement from state $q$.

If we write the string as $w=uv$ where $u$ and $v$ are two sub-strings, then
$$
\delta(q_0,w)=\delta(\delta(q_0,u),v)=\delta(q',v)
$$
where $\delta(q_0,u)=q'$

### Language defined by a DFA
Formally we can say that a DFA $M$ accepts a string $w$ if and only if: 
$$
\delta(q_0,w)\in\bar F
$$
where $q_0$ is the start state and $F$ is the accepting or final state

The language $L(M)$ defined by $M$ is then a set of all strings accepted by $M$.
- It is known as a regular language.
$$
\delta(r_i,a_i)=r_{i+1}\,\,\,\,\text{for } i=0,1,\dots,n-1
$$
