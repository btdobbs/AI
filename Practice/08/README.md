# Practice 8[^1]

For questions with circular bubbles ($\bigcirc$), you may select only one choice.

For questions with square checkboxes ($\square$), you may select one or more choices.

**Please show all work for credit.**

# We Are Getting Close... (8 points)

Mesut is trying to remotely control a car, which has gone out of his view. The unknown state of the car is represented by the random variable $X$. While Mesut can’t see the car itself, his high-tech sensors on the car provides two useful readings: an estimate (E) of the distance to the car in front, and a detection model (D) that detects if the car is headed into a wall. Using these two readings, Mesut applies the controls (C), which determine the velocity of the car by changing the acceleration. The Dynamic Bayes Net below describes the setup.

```mermaid

```

1. For the above DBN, complete the equations for performing updates. (Hint: think about the prediction update and obser- vation update equations in the forward algorithm for HMMs.)

Time elapse: **($i$)** = **($ii$)** **($iii$)** **($iv$)** $P(x_{t-1} \mid e_{0:t-1}, d_{0:t-1}, c_{0:t-1})$

**($i$)**

$\bigcirc$ $P(x_t)$

$\bigcirc$ $P(x_t \mid e_{0:t-1}, d_{0:t-1}, c_{0:t-1})$

$\bigcirc$ $P(e_t, d_t, c_t \mid e_{0:t-1}, d_{0:t-1}, c_{0:t-1})$

**($ii$)**

$\bigcirc$ $P(c_{0:t-1})$

$\bigcirc$ $P(x_{0:t-1}, c_{0:t-1})$

$\bigcirc$ $P(e_{0:t-1}, d_{0:t-1}, c_{0:t-1})$

$\bigcirc$ $P(e_{0:t}, d_{0:t}, c_{0:t})$

$\bigcirc$ 1

**($iii$)**

$\bigcirc$ $\sum_{x_{t-1}}$

$\bigcirc$ $\sum_{x_t}$

$\bigcirc$ $\max_{x_{t-1}}$

$\bigcirc$ $\max_{x_t}$

$\bigcirc$ 1

**($iv$)**

$\bigcirc$ $P(x_{t-1} \mid x_{t-2})$

$\bigcirc$ $P(x_{t-1},x_{t-2})$

$\bigcirc$ $P(x_t \mid e_{0:t-1}, d_{0:t-1}, c_{0:t-1})$

$\bigcirc$ $P(x_t \mid x_{t-1})$

$\bigcirc$ $P(x_t,x_{t-1})$

$\bigcirc$ $P(x_t,e_{0:t-1}, d_{0:t-1}, c_{0:t-1})$

$\bigcirc$ $P(x_t \mid x_{t-1}, c_{t-1})$

$\bigcirc$ $P(x_t,x_{t-1}, c_{t-1})$

$\bigcirc$ 1

Update to incorporate new evidence at time $t$:

$P(x_t \mid e_{0:t}, d_{0:t}, c_{0:t})=$ **($v$)** **($vi$)** **($vii$)** **Your choice for ($i$)**

**($v$)**

$\bigcirc$ $(P(c_t \mid c_{0:t-1}))^-1$

$\bigcirc$ $(P(e_t \mid e_{0:t-1})P(d_t \mid d_{0:t-1})P(c_t \mid c_{0:t-1}))^-1$

$\bigcirc$ $(P(e_t, d_t, c_t \mid e_{0:t-1}, d_{0:t-1}, c_{0:t-1}))^-1$

$\bigcirc$ $(P(e_{0:t-1} \mid e_t)(P(d_{0:t-1} \mid d_t)(P(c_{0:t-1} \mid c_t))^-1$

$\bigcirc$ $(P(e_{0:t-1}, d_{0:t-1}, c_{0:t-1} \mid e_t, d_t, c_t))^-1$

$\bigcirc$ 1

**($vi$)**

$\bigcirc$ $\sum_{x_{t-1}}$

$\bigcirc$ $\sum_{x_t}$

$\bigcirc$ $\sum_{x_{t-1}, x_t}$

$\bigcirc$ $\max_{x_{t-1}}$

$\bigcirc$ $\max_{x_t}$

$\bigcirc$ 1

**($iv$)**

$\square$ $P(x_t \mid e_t, d_t, c_t)$

$\square$ $P(x_t, e_t, d_t, c_t)$

$\square$ $P(x_t \mid e_t, d_t, c_t, c_{t-1})$

$\square$ $P(x_t, e_t, d_t, c_t, c_{t-1})$

$\square$ $P(e_t, d_t \mid x_t)P(c_t \mid e_t, d_t, c_{t-1})$

$\square$ $P(e_t, d_t, c_t \mid x_t)$

$\bigcirc$ 1 

Suppose we want to do the above updates in one step and use normalization to reduce computation. Select all the terms that are *not explicitly calculated* in this implementation.

DO **NOT** include the choices if their values are 1.

$\square$ **($ii$)** $\square$ **($iii$)** $\square$ **($iv$)** $\square$ **($v$)** $\square$ **($vi$)** $\square$ **($vii$)** $\bigcirc$ None of the above

# Planning ahead with HMMs (12 points)

[^1]: [Berkeley Computer Science](http://ai.berkeley.edu)
