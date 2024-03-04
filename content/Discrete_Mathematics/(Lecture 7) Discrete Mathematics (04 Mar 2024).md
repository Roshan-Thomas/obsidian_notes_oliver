---
title: Lecture 7
date: 04 Mar 2024
---
# Axioms
- Mathematics takes an axiomatic approach, where axioms are a collection of well-defined objects and assume some rules about their structure.
- Using axioms, we can derive other information by using logical arguments.
- The axioms should be consistent and there should not be too many of them.
# Statements
A statement should either be true or false.

In proving a statement, we start with an assumption, and then we use our axioms to get a true statement using our *rules of inference*. And we continue the process until we get the statement that we wanted to prove (Goal Statement).
# Propositions, Theorems, Lemmas and Corollaries
- Any statement that we can prove true is called a proposition.
- A proposition of major importance is called a theorem. 
- When we break the proof down into modules, it is called lemmas.
- If we can prove an easy result from a theorem, it is known as corollaries.
# Sets
Sets are a well-defined collection of objects.

An example of sets would be
$$
A=\{1,2,3,4\}
$$
where 
$$
1\in A\,\,\,\,\,\,\,\text{ and }\,\,\,\,\,\, 5\notin A
$$
Another example would be of all integer multiples of 3
$$
3\mathbb{Z}=\{3x:x\in \mathbb{Z}\}
$$
# Euclid's Axioms (or Postulates)
- A straight line segment can be drawn by joining two points.
- Any line segment can be extended indefinitely into a straight line.
- Given any straight line segment, a circle can be drawn having the length of the line segment as the radius and one end of the line segment as its center.
- All right angles are congruent (coincide exactly when superimposed).

# Peano Construction of the Natural Numbers
$$
S:\mathbb{N}\rightarrow\mathbb{N}
$$
$$
n\mapsto n+1
$$
The construction of natural numbers
$$
\begin{array}{cc}0:&0\\ 1:&S(0)\\ 2:&S(S(0))\\ \dots\end{array}
$$
- The last postulate of Peano guarantees us the ability to do proof by induction
## Addition
We define addition as $a+b\equiv P(a,b)$ where $P:\mathbb{N}\times\mathbb{N}\rightarrow \mathbb{N}$
such that 
$$
a+0=a\tag{Rule 1}
$$
$$
a+S(b)=S(a+b)\tag{Rule 2}
$$
# Axiomatic Systems

**First Incompleteness Theorem**
Every axiomatic system (based on a countable number of axioms) contains truth that cannot be proved.

**Second incompleteness theorem**
No axiomatic system (based on a countable number of axioms) can prove its own consistency.

# Groups
Set of object and a binary operator is called a group.

- We have four axioms for a group 
	- (G0) Closure: When you perform an operation on two elements, and your output stays inside the group. $\cdot: G\times G\rightarrow G$
	- (G1) Identity element: $g\cdot e=e\cdot g=g$
	- (G2) Inverse: Every element has an inverse such that $g\cdot g^{-1}=e=g^{-1}\cdot g$  
	- (G3) Associativity 

