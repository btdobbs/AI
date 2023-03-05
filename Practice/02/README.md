# Practice 2[^1]

For questions with circular bubbles ($\bigcirc$), you may select only one choice.

For questions with square checkboxes ($\square$), you may select one or more choices.

**Please show all work for credit.**

# Searching with Heuristics

Consider the $A^\ast$ searching process on the connected undirected graph, with starting node $S$ and the goal node $G$. Suppose the
cost for each connection edge is **always positive**. We define $h^*(𝑋)$ as the shortest (optimal) distance to G from a node $X$.

Answer Questions 1, 2 and 3. You may want to solve Questions 1 and 2 at the same time.

## Question 1

Suppose $h$ is an **admissible** heuristic, and we conduct $A^\ast$ **tree search** using heuristic $h^\prime$ and finally find a solution. Let $𝐶$ be the cost of the found path (directed by $h^\prime$, defined in part (1.1)) from $S$ to $G$

### Question 1.1

Choose **one best** answer for each condition below.

1. If $h^\prime(X) = \frac{1}{2}h(X)$ for all Node $X$, then 

$\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

2. If $h^\prime(X) = \frac{h(X) + h^\ast(X)}{2}$ for all Node $X$, then

$\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

3. If $h^\prime(X) = h(X) + h^\ast(X)$ for all Node $X$, then

$\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

4. If we define the set $K(X)$ for a node $X$ as all its neighbor nodes $Y$ satisfying $h^\ast(X) > h^\ast(Y)$, and the following always holds

$$
\begin{equation}
  h^\prime(X) \le
    \begin{cases}
      \min_{Y \in K(X)} h^\prime(Y) - h(Y) + h(X) & \text{ if } K(X) \ne 0 \\
      h(X) & \text{ if } K(X) = 0 \\
    \end{cases}       
\end{equation}
$$

then,

$\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

5. If $K$ is the same as above, we have

$$
\begin{equation}
  h^\prime(X) \le
    \begin{cases}
      \min_{Y \in K(X)} h(Y) + \text{cost}(X,Y) & \text{ if } K(X) \ne 0 \\
      h(X) & \text{ if } K(X) = 0 \\
    \end{cases}       
\end{equation}
$$

where $\text{cost}(X,Y)$ is the cost of the edge connecting $X$ and $Y$,

then,

$\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

6. If $h^\prime(X) = \min_{Y \in K(X)+\\{X\\}} h(Y)$ ($K$ is the same as above),

$\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

### Question 1.2

In which of the conditions above, $h^\prime$ is still **admissible** and for sure to dominate $h$? Check all that apply. Remember we say $h_1$ dominates $h_2$ when $h1(𝑋)≥h2(𝑋)$ holds for all $X$.  

$\square$ 1 $\square$ 2 $\square$ 3 $\square$ 4 $\square$ 5 $\square$ 6

## Question 2

Suppose $h$ is a **consistent** heuristic, and we conduct $A^\ast$ **graph search** using heuristic $h^\prime$ and finally find a solution.

### Question 2.1

Answer exactly the same questions for each conditions in Question (1.1.i).
    
1. $\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

2. $\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

3. $\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

4. $\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

5. $\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$

6. $\bigcirc$ $C = h^\ast(S)$ $\bigcirc$ $C > h^\ast(S)$ $\bigcirc$ $C \ge h^\ast(S)$
    
### Question 2.2.

In which of the conditions above, $h^\prime$ is still **consistent** and for sure to dominate $h$? Check all that apply.

$\square$ 1 $\square$ 2 $\square$ 3 $\square$ 4 $\square$ 5 $\square$ 6
    
## Question 3

Suppose $h$ is an **admissible** heuristic, and we conduct $A^\ast$ **tree search** using heuristic $h^\prime$ and finally find a solution.  If $\epsilon > 0$, and $X_0$ is a node in the graph, and $h^\prime$ is a heuristic such that

$$
\begin{equation}
  h^\prime(X) \le
    \begin{cases}
      h(X) & \text{ if } X = X_0 \\
      h(X) + \epsilon & \text{ otherwise } \\
    \end{cases}       
\end{equation}
$$

- Alice claims $h^\prime$ can be inadmissible, and hence $C = h^\ast(S)$ does not always hold.
- Bob instead thinks the node expansion order directed by $h^\prime$ is the saem as the heuristic $h^{\prime\prime}$, where

$$
\begin{equation}
  h^{\prime \prime}(X) \le
    \begin{cases}
      h(X) - \epsilon & \text{ if } X = X_0 \\
      h(X) & \text{ otherwise } \\
    \end{cases}       
\end{equation}
$$

Since $h^{\prime\prime}$ is admissible and will lead to $C = h^\ast(S)$, and so does $h^\prime$. Hence, $C = h^\ast(S)$ always holds.
      
The The two conclusions apparently contradict with each other, and **only exactly one of them are correct and the other is wrong.** Choose the **best** explanation from below - which student’s conclusion is wrong, and why are they wrong?
    
$\bigcirc$ Alice’s conclusion is wrong, because the heuristic $h^\prime$ is always admissible.

$\bigcirc$ Alice’s conclusion is wrong, because an inadmissible heuristics does not necessarily always lead to the failure of the optimality when conducting $A^\ast$ tree search.

$\bigcirc$ Alice’s conclusion is wrong, because of another reason that is not listed above.

$\bigcirc$ Bob’s conclusion is wrong, because the node visiting expansion ordering of $h^{\prime\prime}$ during searching might not be the same as $h^\prime$.

$\bigcirc$ Bob’s conclusion is wrong, because the heuristic $h^{\prime\prime}$′ might lead to an incomplete search, regardless of its optimally property.

$\bigcirc$ Bob’s conclusion is wrong, because of another reason that is not listed above.

# CSPs

In this question, you are trying to find a four-digit number satisfying the following conditions:

- the number is odd,
- the number only contains the digits 1, 2, 3, 4, and 5,
- each digit (except the leftmost) is strictly larger than the digit to its left.

## Question 1

We will model this as a CSP where the variables are the four digits of our number, and the domains are the five digits we can choose from. The last variable only has 1, 3, and 5 in its domain since the number must be odd. The constraints are defined to reflect the third condition above. Thus before we start executing any algorithms, the domains are
    
|           |           |           |           |
| --------- | --------- | --------- | --------- |
| 1 2 3 4 5 | 1 2 3 4 5 | 1 2 3 4 5 | 1   3   5 |     
    
1. Before assigning anything, enforce arc consistency. Write the values remaining in the domain of each variable after arc consistency is enforced.

|            |            |            |            |
| ---------- | ---------- | ---------- | ---------- |
| __________ | __________ | __________ | __________ |     


2. With the domains you wrote in the previous part, which variable will the MRV (MinimumRemainingValue) heuristic choose to assign a value to first? If there is a tie, choose the leftmost variable. 

$\bigcirc$ The first digit (leftmost)

$\bigcirc$ The second digit

$\bigcirc$ The third digit

$\bigcirc$ The fourth digit (rightmost)

3. Now suppose we assign to the leftmost digit first. Assuming we will continue filtering by enforcing arc consistency, which value will LCV (Least Constraining Value) choose to assign to the leftmost digit? **Break ties from large (5) to small (1).**

$\square$ 1

$\square$ 2

$\square$ 3

$\square$ 4

$\square$ 5

4. Now suppose we are running min-conflicts to try to solve this CSP. If we start with the number 1332, what will our number be after one interation of min-conflicts? Break variable selection ties from left to right, and **break value selection ties from small (1) to large (5).**

|                            |
| -------------------------- |
| __________________________ |

## Question 2

The following questions are completely unrelated to the above parts. Assume for these following questions, there are only binary constraints unless otherwise specified.

1. When enforcing arcc onsistency in a CSP, the set of values which remain when the algorithm terminates does not depend on the order in which arcs are processed from the queue.

$\bigcirc$ True

$\bigcirc$ False 

2. Once arc consistency is enforced as a pre-processing step, forward checking can be used during backtracking search to maintain arc consistency for all variables.

$\bigcirc$ True

$\bigcirc$ False 

3. In a general CSP with $n$ variables, each taking $d$ possible values, what is the worst case time complexity of enforcing arc consistency using the AC-3 method discussed in class?

$\bigcirc$ $0$

$\bigcirc$ $O(1)$

$\bigcirc$ $O(nd^2)$

$\bigcirc$ $O(n^2d^3)$

$\bigcirc$ $O(d^n)$

$\bigcirc$ $\infty$

4. In a general CSP with 𝑛 variables, each taking 𝑑 possible values, what is the maximum number of times a backtracking search algorithm might have to backtrack (i.e. the number of the times it generates an assignment, partial or complete, that violates the constraints) before finding a solution or concluding that none exists?

$\bigcirc$ $0$

$\bigcirc$ $O(1)$

$\bigcirc$ $O(nd^2)$

$\bigcirc$ $O(n^2d^3)$

$\bigcirc$ $O(d^n)$

$\bigcirc$ $\infty$

5. What is the maximum number of times a backtracking search algorithm might have to backtrack in a general CSP, if it is running arc consistency and applying the MRV and LCV heuristics?

$\bigcirc$ $0$

$\bigcirc$ $O(1)$

$\bigcirc$ $O(nd^2)$

$\bigcirc$ $O(n^2d^3)$

$\bigcirc$ $O(d^n)$

$\bigcirc$ $\infty$

[^1]: [Berkeley Computer Science](http://ai.berkeley.edu)
