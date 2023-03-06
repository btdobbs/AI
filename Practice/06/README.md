# Practice 6[^1]

For questions with circular bubbles ($\bigcirc$), you may select only one choice.

For questions with square checkboxes ($\square$), you may select one or more choices.

**Please show all work for credit.**

# Bayes Nets: Variable Elimination (9 points)

```mermaid
flowchart LR
    id1((A)) --> id3
    id1 --> id2
    id2((B)) --> id5
    id2 --> id4
    id3((C))
    id4((D))
    id5((E))
```

|        |  $P(A)$  |
| ------ | -------- |
|  $+a$  |   0.25   |
|  $-a$  |   0.75   |


|  $P(B \mid A)$ |   $+b$   |   $-b$   |
| -------------- | -------- | -------- |
|       $+a$     |   0.50   |   0.50   |
|       $-a$     |   0.25   |   0.75   |

|  $P(C \mid A)$ |   $+c$   |   $-c$   |
| -------------- | -------- | -------- |
|       $+a$     |   0.20   |   0.80   |
|       $-a$     |   0.60   |   0.40   |

|  $P(D \mid B)$ |   $+d$   |   $-d$   |
| -------------- | -------- | -------- |
|       $+b$     |   0.60   |   0.40   |
|       $-b$     |   0.80   |   0.20   |

|  $P(E \mid B)$ |   $+e$   |   $-e$   |
| -------------- | -------- | -------- |
|       $+b$     |   0.25   |   0.75   |
|       $-b$     |   0.10   |   0.90   |

Using the Bayes’ Net and conditional probability tables above, calculate the following quantities:

1. $P(+b \mid +a) = $  
```


```
2. $P(+a , +b) = $
```


```
3. $P(+a \mid +b) = $
```


```
Now we are going to consider variable elimination in the Bayes’ Net above.

4. Assume we have the evidence $+c$ and wish to calculate $P(E \mid +c)$. What factors do we have initially?
```


```
5. If we eliminate variable $B$, we create a new factor. What probability does that factor correspond to?
```


```
6. What is the equation to calculate the factor we create when eliminating variable $B$?
```


```
7. After eliminating variable $B$, what are the new set of factors? As in (5), write the probabilities that the factors represent. For each factor, also provide its size.
```





```
8. Now assume we have the evidence $-c$ and are trying to calculate $P(A \mid -c)$. What is the most efficient elimination ordering? If more than one ordering is most efficient, provide any one of them.
```


```
9. Once we have run variable elimination and have $f(A,-c)$ how do we calculate $P(+a \mid -c)$?
```


```
# Bayes Nets: Independence (3 points)

[^1]: [Berkeley Computer Science](http://ai.berkeley.edu)
