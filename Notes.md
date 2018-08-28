[TOC]



# **Notes**



# **Concepts**

### *P vs NP*

**P** = Problems with Efficient Algorithms for *Finding* Solutions

**NP** = Problems with Efficient Algorithms for Verifying Proofs/Certificates/Witnesses

**NP-complete**: partition

**NP-hard** (at least as hard as the hardest problems in NP): TSP, "Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city and returns to the origin city?"



### *Master Theorem*

$$
T(n) = a\ T(\frac{n}{b}) + f(n)
$$

 - $n$ is the size of the problem

 - $a$ is the number of subproblem in the recursion

 - $f(n)$ is the time to create the subproblems and combine their results in the above procedure

   Let $c_{crit}=log_{b}a$ ,

   If $f(n) = \Theta(n^{c})\quad where\ c < c_{crit}$



### *RNN*

- GRU

  An update gate, a reset gate.

  If reset is close to 0, ignore previous hidden state.

  Update gate z controls how much of past state should matter now.





- LSTM






# **Some Code**



## Algorithms

### Quick sort

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

### *Zip*

```python
def zip(*iterables):
    # zip('ABCD', 'xy') --> Ax By
    sentinel = object()
    iterators = [iter(it) for it in iterables]
    while iterators:
        result = []
        for it in iterators:
            elem = next(it, sentinel)
            if elem is sentinel:
                return
            result.append(elem)
        yield tuple(result)
```

```python
>>> x = [1, 2, 3]
>>> y = [4, 5, 6]
>>> zipped = zip(x, y)
>>> list(zipped)
[(1, 4), (2, 5), (3, 6)]
>>> x2, y2 = zip(*zip(x, y))
>>> x == list(x2) and y == list(y2)
True
```





## Tricks

### Word to id

```python
word_to_id = dict(zip(words, range(len(words))))
```

### *Inverse dict*

```python
def inverse_dict(dict):
    return {v:k for k,v in dict}
```

### 