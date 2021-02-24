---
title: 'Patchwork Move Maximization Strategy'
author: Chaim Sanders
layout: post
permalink: /move-maximization/
categories:
  - Tech
---
### Naive Approach
The naive answer here, is that the maximum amount of moves would be if the players continued to “step” over each other for the entire game. At that pace, the number of moves in a game would be ceil(n/2+1) for the player and floor(n/2+1) for the opponent where n is the board length. This of course presupposes the collusion of the player (or at minimum lack of a viable strategy on behalf of the opponent).

```
Move 1
A - B - X - X - X - X - X
Move 2
X - X - A - B - X - X - X
Move 3
X - X - X - X - A - B - X
Move 4
X - X - X - X - X - X - A
Move 5
X - X - X - X - X - X - X
```

Assuming a board of length 7 it takes the player 5 turns to reach an end state and the opponent 4 turns to reach an end state

The approach does not consider maximization of pieces and moves, such a situation can be observed when considering pieces with a time cost of 1. Such pieces allow the same player to take an “Extra” piece during a single move. This is the case because when a player lands on top of another player, they may move again.

As a result, while the answer to the initially posed question is ceil(n/2+1), this is only correct assuming the definition of a move is a complete iteration between the player and their opponent

### A definition of a move.
It may therefore become important to redefine a move, not as the completion of the player or opponents turns, nor as the collection of both turns completing, but by the conclusion of a possible buying period (even if the player or opponent has no “button” to buy with).

