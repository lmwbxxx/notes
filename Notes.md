## **Notes**



## **Concepts**

- #### P vs NP

**P** = Problems with Efficient Algorithms for *Finding* Solutions

**NP** = Problems with Efficient Algorithms for Verifying Proofs/Certificates/Witnesses

**NP-complete**: partition

**NP-hard**(at least as hard as the hardest problems in NP): TSP, "Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city and returns to the origin city?"



- #### Master Theorem

$$
T(n) = a\ T(\frac{n}{b}) + f(n)
$$

 - $n$ is the size of the problem

 - $a$ is the number of subproblem in the recursion

 - $f(n)​$ is the time to create the subproblems and combine their results in the above procedure

   Let $c_{crit}=log_{b}a$ ,

   If $f(n) = \Theta(n^{c}) where c < c_{crit}$




## **Some Code**

#### *Quick sort*

```python
# Quick sort
def quicksort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quicksort(left) + middle + quicksort(right)
```




