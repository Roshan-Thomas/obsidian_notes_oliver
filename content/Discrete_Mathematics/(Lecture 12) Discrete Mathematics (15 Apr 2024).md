---
title: Lecture 12
date: 15 Apr 2024
---
# Game Theory
Game theory has its origins in the mid 20th century and originated for military and business applications for strategizing and logistical purposes to get the maximum returns.
- These ideas were used a lot in biology and zoology as well.

- Decisions has to be made by players. 
- Let's say you are playing Scissors, Paper, Rocks, your available actions are 3 options (Scissors, Paper or Rock). The decisions taken by the two players leads to outcomes, and those outcomes are associated with preferences. 
	- In game theory, we need to have clear ordered preferences so we can attribute values to them. Numerical values have to be attached and they are called payoffs. 
	- Different players will have different payoffs. 
	- Our outcomes might involve random chance.
$$
\text{Player 1}\begin{cases}\overbrace{\begin{array}{c|c|c|c|}&\text{Scissor}&\text{Paper}&\text{Rock}\\\hline\text{Scissor}&(0,0)&(1,-1)&(-1,1)\\\text{Paper}&(-1,1)&(0,0)&(1,-1)\\\text{Rock}&(1,-1)&(-1,1)&(0,0)\end{array}}^{\text{Player 2}}\end{cases}
$$

- **Strategy** is how we choose our action.
So what is the strategy for Scissors, Paper, Rock?
- Sometimes strategies need to be probability based to be effective.
- There are different types of strategy that can be taken by the players.
	- *Pure Strategy:* This means definite action (e.g. play scissors all the time)
	- *Mixed Strategy:* This means probabilities of different strategies (example: $50\%$ scissor and $50\%$ Rock)

**Mixed Strategy or anything probabilistic**
- We need to use Expected Value.
	- Expected value is the sum of all payoffs weighted by the probability that they happen.

If we use the 50% Scissor and 50% Rock strategy and the other player also decides to do the same strategy,
$$
\begin{array}{c|c|c|c|}&S&P&R\\\hline S&(0,0)&(1,-1)&(-1,1)\\P&(-1,1)&(0,0)&(1,-1)\\R&(1,-1)&(-1,1)&(0,0)\end{array}
$$
$$
0.25\times 0+0.25\times -1+0.25\times 1+0.25\times 0=0\,\,\,\,\,\,\,\text{which is the same for Player 2}
$$

- The idea behind game theory is that every player is a rational actor.
	- A rational player seeks to *maximize the expected value* of their payoff, and they have no other considerations.

# Nash Equilibrium
Nash Equilibrium is a strategy where no player can improve their expected payoff by changing strategy, even when they know the strategies of all other players.
- The strategy here can be pure or mixed.

Nash proved that for a finite number of players with a finite number of actions each, at least one Nash Equilibrium always exists. 

For example, there is a game called *'Matching Pennies'* where each player has two outcomes Heads or Tails. So if both Player A and Player B gets two heads then they get a prize of (5,5) and if both players get Tails then they both get (2,2) prize.
$$
\begin{array}{c|c|c|}&H_B&T_B\\\hline H_A&(5,5)&(-1,-1)\\T_A&(-1,-1)&(2,2)\end{array}
$$
HH gives both players 5, and is really happy.
But this is NOT the only Nash Equilibrium. TT is also a Nash Equilibrium, because if we tell the other player in advance that we are playing Tails then the other players best action is also to play Tails. 

So just becomes one is the Nash equilibrium doesn't mean that is the best option, there may be other Nash equilibriums. 

## Dominated Strategies
We say a strategy of a player is *dominated* by another strategy if the other strategy always gives a higher payoff, regardless of the behavior of the other players. 

Lets say Player A is a very powerful hegemonic nation and their president, and Player B is a smaller nation that is in/and causing a spot of bother. Player A can either supply arms to Player B or not supply arms. And Player B can behave aggressively or not behave aggressively.

$$
\begin{array}{c|cc|}&\text{behave aggressively}&\text{NOT behave aggressively}\\\hline \text{supply arms}&(2,4)&(4,3)\\\text{not supply arms}&(1,1)&(3,2)\end{array}
$$
- In the first column, 2 beats 1 for Player A.
- In the second column, 4 beats 3 for Player A.

This is an example of dominated strategies as regardless of Player B's actions, the first row is always better for Player A (supply arms).


**NOTE:** The first thing you have to do in a game theory problem is to look for dominated strategies and exclude them. 