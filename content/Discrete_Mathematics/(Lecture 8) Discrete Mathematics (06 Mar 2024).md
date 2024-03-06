---
title: Lecture 8
date: 06 Mar 2024
---
## Recap
The properties of a group are Closure, Associativity, Identity, Inverses, and Commutativity (not present in all groups, unless they are special). 

## Example
A set 
$$
G=\{T,L\}
$$
where $T$ is a truth and $L$ is a lie.
We define a semantic operation
$$
\cdot:G\times G\rightarrow G
$$
such that
$$
\begin{array}{c}T\cdot a=a\\ L\cdot a=\bar a\end{array}\,\,\,\,\,\, a\in G\text{ Opposite of a is $\bar a$}
$$

$$
\begin{array}{c|c|c}\cdot&T&L\\\hline T&T&L\\L&L&T\end{array}
$$

We now have to check the four properties
**Closure:** Yes, we have closure.

**Associative**
We have to check 
$$
(a\cdot b)\cdot c=a\cdot (b\cdot c)
$$
Since the number of entries are limited, we can exhaustively check it
$$
\begin{array}{c|c|c|c|c}a&b&bc&(a\cdot b)\cdot c&a\cdot(b\cdot c)\\\hline T&T&T&&\\T&T&L&&&\\\vdots\end{array}
$$
This is similar to doing a truth table 

**Identity**
The identity element is Truth $T$
$$
e=T
$$

**Inverse**
$$
T\cdot T^{-1}=e
$$
$$
T^{-1}\cdot T=e
$$
Truth is its own inverse

The inverse for lie is also itself
$$
L^{-1}=L
$$
## Example
We consider permutations of $n$ objects
$$
G_n=\text{set of ordered n-tuples containing $1,\dots,n$}
$$

So for example
$$
G_2=\{(1,2),(2,1)\}
$$
$$
G_3=\{(1,2,3),(1,3,2),(2,1,3),(2,3,1),(3,1,2),(3,2,1)\}
$$

We define our operator 
$$
\cdot: G_n\times G_n\rightarrow G_n
$$
$$
a\cdot b=c\,\,\,\,\,\,\text{ where }a,b,c\in G_n
$$
$$
c_i=a_{b_i}
$$
This means that 
$$
\begin{split}\underbrace{(1,2,3)}_{a}\cdot\underbrace{(3,2,1)}_b&=(a_{b_1},a_{b_2},a_{b_3})\\&=(a_3,a_2,a_1)\\&=(3,2,1)\end{split}
$$


**Is this a group?**

We have to check the properties

1. **Closure**
Yes, we have closure

2. Associative
This means that 
$$
a\cdot(b\cdot c)=(a\cdot b)\cdot c
$$
Here doing it exhaustively is an arduous process, so we show this in a general sense.
$$
\begin{split}LHS&=[a\cdot(b\cdot c)]\\&=a_{(b\cdot c)_i}\\&=a_{b_{c_i}}\end{split}\,\,\,\,\,\begin{split}RHS&=[(a\cdot b)\cdot c]\\&=(a\cdot b)_{c_i}\\&=a_{b_{c_i}}\end{split}
$$
$$
RHS=LHS
$$
So we have associativity

3. **Identity**
We have to show that
$$
e\cdot a=a
$$
$$
a\cdot e=a
$$

So,
$$
\begin{array}{cc}(e\cdot a)_i=a_i& (a\cdot e)_i=a_i\\ e_{a_i}=a_i& a_{e_i}=a_i\end{array}
$$
We can try and show this for a particular example 
$$
(e_1,e_2,e_3)\cdot (a_1,a_2,a_3)=(a_1,a_2,a_3)
$$
$$
\begin{array}{cc}e_{a_1}=a_1&a_{e_1}=a_1\\ e_{a_2}=a_2& a_{e_2}=a_2\\ e_{a_3}=a_3& a_{e_3}=a_3\end{array}
$$
So,
$$
e=(1,2,\dots, n)
$$

4. **Inverses**
$$
a\cdot a^{-1}=e\,\,\,\,\,\,\,\text{ and }\,\,\,\,\,\, a^{-1}\cdot a=e
$$
Let $a^{-1}=b$ (for convenience of notation)

The $i^{th}$ component
$$
a_{b_i}=i\,\,\,\,\,\,\,\text{ and }\,\,\,\,\, b_{a_i}=i
$$
$$
(a_1,a_2,a_3)\cdot (b_1,b_2,b_3)=(1,2,3)
$$
$$
\begin{array}{cc}a_{b_1}=1& b_{a_1}=1\\ a_{b_2}=2& b_{a_2}=2\\ a_{b_3}=3& b_{a_3}=3\end{array}
$$
So,
$$
b_i=j\,\,\,\text{such that }a_j=i
$$
Taking an example
$$
(3,1,2)\cdot\underbrace{(2, 3, 1)}_{\text{inverse}}=(1,2,3)
$$

So, we have shown that $G_n$ is a group.
___
## Recap: Subgroups and Cyclic Groups
In the lecture notes, 
$\mathbb{Z}_n$ modular $n$ under addition in a group

$\mathbb{N}_8$ under addition mod 8
$$
G=\{0,1,2,3,4,5,6,7\}
$$
$$
H=\{0,4\}
$$
So $H$ is a subgroup of $G$
$$
H\subseteq G\,\,\,\,\text{and }\,\,\,\, H\subset G
$$

