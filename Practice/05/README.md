# Practice 5[^1]

For questions with circular bubbles ($\bigcirc$), you may select only one choice.

For questions with square checkboxes ($\square$), you may select one or more choices.

**Please show all work for credit.**

# Policy Evaluation

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
You can use any of the terms $Q, s_t, s_{t+1}, a_t, a_{t+1}, r_t, r_{t+1}, \gamma, \alpha, \pi$ in your equation, as well as $\sum$ and max with any index variables (i.e. you could write $\max_{\alpha}$, or $\sum_{\alpha}$ and then use $\alpha$ somewhere else), but no other terms.

$$
Q(s_t,a_t) \leftarrow (1 - \alpha)Q(s_t, \alpha_t) + \alpha[]
$$

3. 3

# MDPs & RL

[^1]: [Berkeley Computer Science](http://ai.berkeley.edu)
