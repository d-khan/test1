# Q2 Nim with "reinforcement learning" (40 marks)

---
## Background

Here we continue with PS11 Q2, but this time we will create "learning" players inspired by reinforcement learning: The players will 'reward' the winning choices and "punish" the losing choices.

Like the naive players, the learning players will make their choices randomly. Unlike the naive players who assign equal probability to all 3 choices (1, 2, 3 sticks), the learning players increase the probability of selecting the winning choice and reduce the probability of the losing choice. For example, if we have seen from previous rounds that when there are 8 sticks available if we select 3 sticks we are more likely to win than other choices, then instead of choosing between 1, 2, or 3 sticks with equal probability, we should select 3 sticks with higher probability.

To be able to do so, we need to have some data structure to store and update the probability information. We can do so by a `dict` of `dict` (say it is called `_net_wins`) like the following (it does not need to be exactly like the following. You can for example start the map with key 1 instead of 5, or use a `list` of `list`):
```
{5: {1: 0, 2: 0, 3: 0},
 6: {1: 0, 2: 0, 3: 0},
 7: {1: 0, 2: 0, 3: 0},
 8: {1: 0, 2: 0, 3: 0},
 ...
 100: {1: 0, 2: 0, 3: 0},
}
```
The key is the number of sticks available, and the value is another `dict`, for which it stores the number of net wins attributed to each choice (1, 2 or 3). All values should be set to 0 at the beginning, as the net wins for each choice is 0.

To illustrate how the information stored in `_net_wins` can be used to select the number of sticks and how to update it after a around, let us assume after many rounds `_net_wins` is now:

```
{5: {1: -23, 2: -25, 3: -25},
 6: {1: 32, 2: -4, 3: -1},
 7: {1: 0, 2: 132, 3: -2},
 8: {1: -2, 2: 3, 3: 130},
 ...
 100: {1: 6, 2: -3, 3: 113}
}
```

**i. How to select the number of sticks:**

Suppose now 8 sticks are available and we need to select the number of sticks to take. Based on this information, we should select 3 sticks with high probability (as the corresponding net wins has high value) and 1 and 2 with low probability. We calculate the probability by:

* P(select 1) = max(1, net win for selecting 1)/[max(1, net win for selecting 1)+max(1, net win for selecting 2)+max(1, net win for selecting 3) = 1/(1+3+130) = 0.0074
* P(select 2) = max(1, net win for selecting 2)/[max(1, net win for selecting 1)+max(1, net win for selecting 2)+max(1, net win for selecting 3) = 3/(1+3+130) = 0.0224
* P(select 3) = max(1, net win for selecting 3)/[max(1, net win for selecting 1)+max(1, net win for selecting 2)+max(1, net win for selecting 3) = 130/(1+3+130) = 0.9702

Then randomly select 1, 2 or 3 based on the probability above.

Similarly, if 7 sticks are available, then we have:
* P(select 1) = 1/(1+132+1)
* P(select 2) = 132/(1+132+1)
* P(select 3) = 1/(1+132+1)

**ii. How to update `_net_wins`:**
1. For each round, store all moves
2. Once the round is done, update `_net_wins`:
  * If the round is won, increase the net win by one for the corresponding moves
    * For example, if the moves are `{100: 1, ..., 8: 3}` with each key the number of sticks available and value the number of sticks selected, then the `_net_wins` above will become:
    ```
    {5: {1: -23, 2: -25, 3: -25},
     6: {1: 32, 2: -4, 3: -1},
     7: {1: 0, 2: 132, 3: -2},
     8: {1: -2, 2: 3, 3: 131},
     ...
     100: {1: 7, 2: -3, 3: 113}
    }
    ```
  * If the round is lost, decrease the corresponding net win by one
    * For example, if the moves are {100: 2, ..., 7: 1, 5: 2}, then the `_net_wins` above will the following:
    ```
    {5: {1: -23, 2: -26, 3: -25},
     6: {1: 32, 2: -4, 3: -1},
     7: {1: -1, 2: 132, 3: -2},
     8: {1: -2, 2: 3, 3: 131},
     ...
     100: {1: 7, 2: -4, 3: 113}
    }
    ```
---
## Description

0. (preparation step) Put your code for the class definition of `Player` and `SmartPlayer` from PS11 into `src/nim.py`. You are allowed to modified your code so that it is different from the PS11, but please do not copy from the solution (directly)
1. Write a class `LearningPlayer` in `src/nim.py`. Its instances represent "learning" players using the "reinforcement learning" strategy described above. This class should have the same methods available as `Player`, but the behaviour of `play()` is different
2. In the report, demonstrate the performance of some instances of `LearningPlayer` by playing some games with some instances of `Player` and `SmartPlayer`. Do you think the `LearningPlayer` works?

  You may also try to answer the following question:
  * What is a good strategy to "train" an instance of `LearningPlayer`? To play with a naive player or a smart player?
  * How quickly does the learning player learn when playing with a naive player?
  * Can the learning players be as good as the smart players? Why and why not? If it is not, can you think of ways to improve learning players?

  Feel free to do further analysis or interpret the results with what you have learned from other courses.

---
## Coding description and additional requirements

* Please make sure you demonstrate the OOP concepts in this task
* Feel free to reuse the code for the game playing you have submitted for PS11, but please do not copy from the solution (directly). You can rewrite the code if you want to as well

---
## Things to show in the report

* Part 2 as instructed above. Please make sure you include the "explanation" or "interpretation" of your result
