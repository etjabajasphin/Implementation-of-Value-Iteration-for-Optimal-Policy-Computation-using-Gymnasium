# Implementation-of-Value-Iteration-for-Optimal-Policy-Computation-using-Gymnasium

---
## Aim

To implement the **Value Iteration** algorithm for solving a finite Markov Decision Process using the Gymnasium `FrozenLake-v1` environment, and to compute the optimal state-value function and optimal policy using the Bellman optimality equation.

---

## Problem Statement

The `FrozenLake-v1` environment contains a grid of frozen tiles, holes, a start state, and a goal state. The agent must learn the best action to take from each state in order to reach the goal safely.

The objective of this experiment is to:

1. Represent the FrozenLake environment as a finite Markov Decision Process.
2. Apply the Value Iteration algorithm.
3. Compute the optimal state-value function $V^*(s)$.
4. Extract the optimal policy $pi^*(s)$.
5. Display the value function and policy in grid form.

---

## Software Requirements

```bash
pip install gymnasium numpy matplotlib
```

---

## Environment Description

This experiment uses the Gymnasium `FrozenLake-v1` environment.

FrozenLake is a grid-world environment where the agent moves across frozen tiles and tries to reach the goal without falling into holes.

For the default 4 x 4 FrozenLake map:

| Component | Description |
|---|---|
| Environment | `FrozenLake-v1` |
| Map size | 4 x 4 |
| Observation space | 16 discrete states |
| Action space | 4 discrete actions |
| Actions | 0 = Left, 1 = Down, 2 = Right, 3 = Up |
| Reward | +1 for reaching the goal, 0 otherwise |
| Terminal states | Goal and hole states |
| Transition model | Accessed using `env.P[state][action]` |

---

## MDP Representation

A Markov Decision Process is represented as:

$$
MDP = (S, A, P, R, \gamma)
$$

Where:

| Symbol | Meaning |
|---|---|
| $S$ | Set of states |
| $A$ | Set of actions |
| $P(s' \mid s,a)$ | Transition probability |
| $R(s,a,s')$ | Reward function |
| $gamma$ | Discount factor |

---

## Theory

Value Iteration is used to directly compute the optimal value function.

Unlike Policy Iteration, Value Iteration does not separately perform full policy evaluation and policy improvement. Instead, it combines both ideas using the Bellman optimality update.

The Bellman optimality equation is:

$$
V^*(s) =
\max_a
\sum_{s'} P(s' \mid s,a)
\left[
R(s,a,s') + \gamma V^*(s')
\right]
$$

After the value function converges, the optimal policy is extracted using:

$$
\pi^*(s) =
\arg\max_a
\sum_{s'} P(s' \mid s,a)
\left[
R(s,a,s') + \gamma V^*(s')
\right]
$$

Where:

| Symbol | Meaning |
|---|---|
| $s$ | Current state |
| $a$ | Action |
| $s'$ | Next state |
| $P(s' \mid s,a)$ | Probability of reaching state $s'$ after taking action $a$ in state $s$ |
| $R(s,a,s')$ | Reward received after the transition |
| $gamma$ | Discount factor |
| $V^*(s)$ | Optimal value of state $s$ |
| $\pi^*(s)$ | Optimal policy |

---

## Algorithm

1. Create the Gymnasium `FrozenLake-v1` environment.
2. Initialize the state-value function $V(s)=0$ for all states.
3. For every state:
   - Compute the expected value of each possible action.
   - Select the maximum action value.
   - Update the value of the state.
4. Repeat the update process until the maximum change in value is less than a small threshold $theta$.
5. After convergence, extract the optimal policy by selecting the best action for each state.
6. Display the optimal value function and optimal policy.

---

## Python Program

```python

# -------------------------------------------------
# Value Iteration Algorithm
# -------------------------------------------------
# Write your code here
```

---

## Output

```text

Number of Iterations: 

Optimal State-Value Function:



Optimal Policy:

```

---

## Result
```text
Write your result here

```
---

## Inference
```text
Write the inference here


```
---

