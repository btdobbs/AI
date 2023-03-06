# Practice 5[^1]

For questions with circular bubbles ($\bigcirc$), you may select only one choice.

For questions with square checkboxes ($\square$), you may select one or more choices.

**Please show all work for credit.**

# Policy Evaluation (4 points)

In this question, you will be working in an MDP with states $S$, actions $A$, discount factor $\gamma$, transition function $T$, and reward
function $R$.

We have some fixed policy $\pi : S \rightarrow A$, which returns an action $a = \pi(s)$ for each state $s \in S$. We want to learn the $Q$ function $Q\pi(s,a)$ for this policy: the expected discounted reward from taking action $a$ in state $s$ and then continuing to act according to:

$$
\pi : Q^{\pi}(s,a) = \sum_{s^{\prime}} T(s,a,s^{\prime})[R(s,a,s^{\prime}) + \gamma Q^{\pi}(s^{\prime},\pi(s^{\prime})]
$$

The policy $\pi$ will not change while running any of the algorithms below.

1. Can we guarantee anything about how the values $Q^{\pi}$ compare to the values $Q^{\ast}$ for an optimal policy $\pi^{\ast}$?

$\bigcirc$ $Q^{\pi}(s,a) \le Q^{\ast}(s,a) \forall s,a$

$\bigcirc$ $Q^{\pi}(s,a) = Q^{\ast}(s,a) \forall s,a$

$\bigcirc$ $Q^{\pi}(s,a) \ge Q^{\ast}(s,a) \forall s,a$

$\bigcirc$ None of the above are guaranteed

Suppose $T$ and $R$ are *unknown*. You will develop sample-based methods to estimate $Q^{\pi}$.  You obtain a series of *samples* $(s_1, a_1, r_1),(s_2, a_2, r_2), \cdots ,(s_T, a_T, r_T)$ from acting according to this policy (where $a_1 = \pi(s_t) \forall t$).

2. Recall the update equation for the Temporal Difference algorithm, performed on each sample in sequence:

$$
V(s_t) \leftarrow (1 - \alpha)V(s_t) + \alpha(r_t +  \gamma V(s_{t+1}))
$$

which approximates the expected discounted reward $V^{\pi} (s)$ for following policy $\pi$ from each state $s$, for a learning
rate $\alpha$.

Fill in the blank below to create a similar update equation which will approximate $Q^{\pi}$ using the samples.
You can use any of the terms $Q, s_t, s_{t+1}, a_t, a_{t+1}, r_t, r_{t+1}, \gamma, \alpha, \pi$ in your equation, as well as $\sum$ and max with any index variables (i.e. you could write $\max_a$, or $\sum_a$ and then use $a$ somewhere else), but no other terms.

$$
Q(s_t,a_t) \leftarrow (1 - \alpha)Q(s_t, a_t) + \alpha \[  \rule{10cm}{0.15mm}  \]
$$

3. Now, we will approximate $Q^{\pi}$ using a linear function: $Q(s,a) = \vec{w}^Tf(s,a)$ for a weight vector $\vec{w}$ and feature function $f(s,a)$. To decouple this part from the previous part, use $Q_{\text{samp}}$ for the value in the black in part (2) (i.e. $Q(s_t,a_t) \leftarrow (1-\alpha)Q(s_t,a_t) + \alpha Q_{\text{samp}})$.

Which of the following is the correct sample-based update for $\vec{w}$?

$\bigcirc$ $\vec{w} \leftarrow \vec{w} + \alpha \[ Q(s_t, a_t) - Q_{\text{samp}} \]$

$\bigcirc$ $\vec{w} \leftarrow \vec{w} - \alpha \[ Q(s_t, a_t) - Q_{\text{samp}} \]$

$\bigcirc$ $\vec{w} \leftarrow \vec{w} + \alpha \[ Q(s_t, a_t) - Q_{\text{samp}} \]f(s_t,a_t)$

$\bigcirc$ $\vec{w} \leftarrow \vec{w} - \alpha \[ Q(s_t, a_t) - Q_{\text{samp}} \]f(s_t,a_t)$

$\bigcirc$ $\vec{w} \leftarrow \vec{w} + \alpha \[ Q(s_t, a_t) - Q_{\text{samp}} \]\vec{w}$

$\bigcirc$ $\vec{w} \leftarrow \vec{w} - \alpha \[ Q(s_t, a_t) - Q_{\text{samp}} \]\vec{w}$

4. The algorithms in the previous parts (part 2 and 3) are:

$\bigcirc$ model-based

$\bigcirc$ model-free

# MDPs & RL (5 points)

![gw](https://github.com/btdobbs/AI/blob/main/Practice/05/gw.png)

Consider the grid-world MDP above. The goal of the game is to reach the pot of gold. As soon as you land on the pot of gold you receive a reward and the game ends. Your agent can move around the grid by taking the following actions: North, South, East, West. Moving into a square that is not a wall is always successful. If you attempt to move into a grid location occupied by a wall or attempt to move off the board, you remain in your current grid location.

Our goal is to build a value function that assigns values to each grid location, but instead of keeping track of a separate number for each location, we are going to use features. Specifically, suppose we represent the value of state $(x,y)$ (a grid location) as $V(x,y) = w^T f(x,y)$. Here, $f(x,y)$ is a feature function that maps the grid location $(x,y)$ to a vector of features and $w$ is a weight vector that parameterizes our value function (note that entries in $w$ can be any real number, positive or negative).

In the next few questions, we will look at various possible feature functions $f(x,y)$. We will think about the value functions that are representable using each set of features, and, further, think about which policies could be extracted from those value functions. Assume that when a policy is extracted from a value function, ties can be broken arbitrarily. In our definition of feature functions we will make use of the location of the pot of gold. Let the gold’s location be $(x^{\ast},y^{\ast})$. Keep in mind the policies (*i*), (*ii*), (*iii*), (*iv*), (*v*), and (*vi*) shown below.

![gw-q](https://github.com/btdobbs/AI/blob/main/Practice/05/gw-q.png)

1. Suppose we use a single feature: the x-distance to the pot of gold. Specifically, suppose $f(x,y) = | x - x^{\ast}|$. Which of the policies could be extracted from a value function that is representable using this feature function? Assume the weights vector $w$ is not allowed to be 0. Fill in all that apply.

$\square$ (*i*) $\square$ (*ii*) $\square$ (*iii*) $\square$ (*iv*) $\square$ (*v*) $\square$ (*vi*)

2. Suppose we use a single feature: the y-distance to the pot of gold. Specifically, suppose $f(x,y) = | y - y^{\ast}|$. Which of the policies could be extracted from a value function that is representable using this feature function? Assume the weights vector $w$ is not allowed to be 0. Fill in all that apply.

$\square$ (*i*) $\square$ (*ii*) $\square$ (*iii*) $\square$ (*iv*) $\square$ (*v*) $\square$ (*vi*)

3. Suppose we use a single feature: the Manhattan distance to the pot of gold. Specifically, suppose $f(x,y) = | x - x^{\ast}| + | y - y^{\ast}|$. Which of the policies could be extracted from a value function that is representable using this feature function? Assume the weights vector $w$ is not allowed to be 0. Fill in all that apply.

$\square$ (*i*) $\square$ (*ii*) $\square$ (*iii*) $\square$ (*iv*) $\square$ (*v*) $\square$ (*vi*)

4. Suppose we use a single feature: the length of the shortest path to the pot of gold. Which of the policies could be extracted from a value function that is representable using this feature function? Assume the weights vector $w$ is not allowed to be 0. Fill in all that apply.

$\square$ (*i*) $\square$ (*ii*) $\square$ (*iii*) $\square$ (*iv*) $\square$ (*v*) $\square$ (*vi*)

5. Suppose we use a single feature: the x-distance to the pot of gold and the y-distance to the pot of gold. Specifically, suppose $f(x,y) = (| x - x^{\ast}|,  | y - y^{\ast}|)$. Which of the policies could be extracted from a value function that is representable using this feature function? Assume the weights vector $w$ is not allowed to be 0. Fill in all that apply.

$\square$ (*i*) $\square$ (*ii*) $\square$ (*iii*) $\square$ (*iv*) $\square$ (*v*) $\square$ (*vi*)

[^1]: [Berkeley Computer Science](http://ai.berkeley.edu)
