---
title: Lecture 13
date: 17 Apr 2024
---
# Game Theory
- A general principle of game theory is that all players know everything about how the game works, but what you don't know is how they decide to play the game.
- Nash equilibrium - Each player's strategy is the best response to all other player's strategy.
	- The best response means that I couldn't do better by changing any strategy.
# Prisoner's dilemma
There are two options for two prisoners to cooperate with each other or defect and give evidence. If they both cooperate they both spend time in jail for a year, but if one of them defects and the other stays silent then the other prisoner gets 10 years in jail and the one who defected gets to go scot-free. But if both decide to defect (give information on each other) then they both get 8 years in prison.
$$
\begin{array}{c|c|c}&C&D\\\hline\text{Cooperate (with each other)}&(-1,-1)&(-10,0)\\\text{Defect (and give evidence)}&(0,-10)&(-8,-8)\end{array}
$$
CC cannot be a Nash equilibrium because If I knew that my opponent is cooperating my best response is to defect. 

So, D dominates C for both players. This is a dominating strategy.

**N.B.** If you have a large game, your first step would be to decide if there are any dominating strategies, and eliminate it, to get a simpler game.
## Zero-sum games
A zero-sum game is a game with two players where the sum of the payoffs is zero for any combo of actions. 

An example would be if someone asked you to pick a card and its either a king or a queen, and they also do the same. And if both of you pick king, they have to give 3 pounds to you, and if you both pick queens, you get 2 pounds. 
$$
\text{A }\begin{cases}\overbrace{\begin{array}{c|c|c}&K&Q\\\hline K&(-3,3)&(5,-5)\\Q&(1,-1)&(2,-2)\end{array}}^B\end{cases}
$$
Written more simply by just showing payoffs to player A.
$$
\begin{array}{c|c|c}&K&Q\\\hline K&-3&5\\Q&1&2\end{array}
$$
For Player B, K dominates Q.

And the sole Nash equilibrium is $[Q,K]$

So, the value of the game to Player A is simply 1.

In general, to find the Nash equilibrium of a zero-sum game, I want to pick my actions or strategies to make the *worst* that can happen as *good* for me as possible.
- This is known as the **Minimax Principle**

### Minimax Principle
The aim of this principle is to minimize the maximum loss, OR maximize the minimum gain, OR make the worst as good as possible. 

For example, let's take a game between Cam and Andreea
$$
\text{Cam }\overbrace{\begin{cases}\begin{array}{c|ccc}&K&Q&J\\\hline K&5&0&-6\\Q&-4&-2&3\\J&4&\boxed{1}&2\end{array}\end{cases}}^{\text{Andreea}}
$$
The option of choosing Queen by Andreea and Jack by Cam is a Nash equilibrium. This is also known as the saddle point. 
____
Lets take another game, where Cam and Andreea has to pick between Heads or Tails
$$
\text{Cam }\overbrace{\begin{cases}\begin{array}{c|cc}&H&T\\\hline H&2&4\\T&3&1\end{array}\end{cases}}^{\text{Andreea}}
$$
In no way does Andreea every get a good pure strategy to win in this game. And it can clearly be seen that there is no saddle point. This means that the Nash equilibrium will have to involve mixed strategies. 

So the task is to *find* the mixed strategy, and the expected payoffs to both players.

So the **approach**,
Let's call the payoff matrix $R=\begin{pmatrix}2&4\\3&1\end{pmatrix}$ (Note: R needs to have all positive elements for this to be guaranteed to work)

It turns out that finding the best strategy for Player B (Andreea) is equivalent to this problem. 

Find a vector $\vec y$ that maximizes $\begin{pmatrix}1&1\end{pmatrix}\begin{pmatrix}y_1\\y_2\end{pmatrix}$ i.e. $y_1+y_2$
given the constraints $\vec y\ge 0$ (element wise)
$$
R\,\,\,\vec y\le 1\text{ i.e. }\begin{pmatrix}1\\1\end{pmatrix}\text{ (element wise)}
$$
The interpretation is that the best value of $y_1+y_2=\frac{1}v$ gives the reciprocal of the expected payoff to player A.

And
$$
y_1\equiv \frac{\text{Prob of Player B using Action 1}}{v}\,\,\,\,\,\,\,\,\,y_2=\frac{\text{Prob of Player B using ACtion 2}}{v}
$$
And by magic, the method that we'll use to solve these given the probability of Player A doing the actions.

The above problem can be written in a Tableau format
$$
\begin{array}{ccccc|c}2&4&1&0&0&1\\3&1&0&1&0&1\\\hline -1&-1&0&0&1&0\end{array}
$$
We can do row operations in a very specific way to get rid of the negatives on bottom row while always positive in RH column.
