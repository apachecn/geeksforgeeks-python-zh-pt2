# Python 程序寻找给定和的所有可能对

> 原文:[https://www . geesforgeks . org/python-program-to-find-all-可能的对-with-given-sum/](https://www.geeksforgeeks.org/python-program-to-find-all-possible-pairs-with-given-sum/)

给定一个整数列表和一个整数变量 *K* ，编写一个 Python 程序，用给定的和 *K* 找到列表中的所有对。

**示例:**

```py
Input : lst =[1, 5, 3, 7, 9]
        K = 12
Output : [(5, 7), (3, 9)]

Input : lst = [2, 1, 5, 7, -1, 4]
        K = 6
Output : [(2, 4), (1, 5), (7, -1)]

```

**方法#1 :** 皮托尼天真

这是解决上述问题的一种幼稚的方法。首先，我们取一个空列表“res”，开始一个循环，遍历给定整数列表的每个元素。在每次迭代中，弹出元素，将其存储在‘num’中，找到总和 K 的剩余差值，并检查该差值是否存在于给定列表中。

```py
# Python3 program to find all pairs in 
# a list of integers with given sum 

def findPairs(lst, K): 
    res = []
    while lst:
        num = lst.pop()
        diff = K - num
        if diff in lst:
            res.append((diff, num))

    res.reverse()
    return res

# Driver code
lst = [1, 5, 3, 7, 9]
K = 12
print(findPairs(lst, K))
```

**Output:**

```py
[(5, 7), (3, 9)]

```

**方法 2 :** 使用`collections.Counter`

这种方法遵循与上面使用`collections.Counter`讨论的方法相同的方法。

```py
# Python3 program to find all pairs in 
# a list of integers with given sum 
from collections import Counter

def findPairs(lst, K): 
    res = []
    count = Counter(lst)

    for x in lst:
        y = K - x
        if (x != y and count[y]) or (x == y and count[y] > 1):
            res.append((x, y)) 
            count.subtract((x, y))

    return res

# Driver code
lst = [1, 5, 3, 7, 9]
K = 12
print(findPairs(lst, K))
```

**Output:**

```py
[(5, 7), (3, 9)]

```

**法#3 :** `itertools.combinations`(天真法)

这是一种天真的使用`itertools.combinations`的方法。我们使用 for 循环遍历每个组合，找出想要的组合。

```py
# Python3 program to find all pairs in 
# a list of integers with given sum 

from itertools import combinations

def findPairs(lst, K):   
    res = []
    for var in combinations(lst, 2):
        if var[0] + var[1] == K:
            res.append((var[0], var[1]))

    return res

# Driver code
lst = [1, 5, 3, 7, 9]
K = 12
print(findPairs(lst, K))
```

**Output:**

```py
[(5, 7), (3, 9)]

```

**方法#4 :** `itertools.combinations`(高效方法)

```py
# Python3 program to find all pairs in 
# a list of integers with given sum 
from itertools import combinations

def findPairs(lst, K):

    return [pair for pair in combinations(lst, 2) if sum(pair) == K]

# Driver code
lst = [1, 5, 3, 7, 9]
K = 12
print(findPairs(lst, K))
```

**Output:**

```py
[(5, 7), (3, 9)]

```