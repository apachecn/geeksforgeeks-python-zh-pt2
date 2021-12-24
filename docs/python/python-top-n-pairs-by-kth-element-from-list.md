# Python |列表中第 Kth 个元素的前 N 对

> 原文:[https://www . geesforgeks . org/python-top-n-pairs-by-kth-element-from-list/](https://www.geeksforgeeks.org/python-top-n-pairs-by-kth-element-from-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要获取记录的第 Kt 个元素所过滤的元素的最大值。这在 web 开发领域有着非常重要的用途。让我们讨论执行这项任务的某些方法。

**方法一:使用`filter() + lambda + set()` +列表理解**

上述功能的组合可用于执行该特定功能。在这种情况下，我们首先从 Kth 索引中过滤前 N 个元素，然后将这些值应用于列表并返回结果。

```
# Python3 code to demonstrate working of
# Top N pairs by Kth element from list
# Using filter() + lambda + set() + list comprehension

# initialize list 
test_list = [('gfg', 4, 'good'), ('gfg', 2, 'better'), 
             ('gfg', 1, 'best'), ('gfg', 3, 'geeks')]

# printing original list
print("The original list is : " + str(test_list))

# initialize N 
N = 3 

# initialize K 
K = 1

# Top N pairs by Kth element from list
# Using filter() + lambda + set() + list comprehension
temp = set(list({sub[K] for sub in test_list})[-N:])
res = list(filter(lambda sub: sub[K] in temp, test_list))

# printing result
print("Top N elements of Kth index are : " + str(res))
```

**Output :**

> 原列表为:[('gfg '，4，' good ')，(' gfg '，2，' better ')，(' gfg '，1，' best ')，(' gfg '，3，' geeks')]
> Kth 索引的前 N 个元素为:[('gfg '，4，' good ')，(' gfg '，2，' better ')，(' gfg '，3，' geeks ')]

**方法 2:使用`groupby() + sorted()` +循环**

该任务也可以使用上述功能来执行。在这种情况下，我们首先将前 N 个元素组合在一起，然后在构建结果列表时用 N 进行限制。

```
# Python3 code to demonstrate working of
# Top N pairs by Kth element from list
# Using groupby() + sorted() + loop
import itertools

# initialize list 
test_list = [('gfg', 4, 'good'), ('gfg', 2, 'better'),
             ('gfg', 1, 'best'), ('gfg', 3, 'geeks')]

# printing original list
print("The original list is : " + str(test_list))

# initialize N 
N = 3 

# initialize K 
K = 1

# Top N pairs by Kth element from list
# Using groupby() + sorted() + loop
res = []
temp = itertools.groupby(sorted(test_list, key = lambda sub : sub[K], 
                          reverse = True), key = lambda sub : sub[K])
for i in range(N):
    res.extend(list(next(temp)[K]))

# printing result
print("Top N elements of Kth index are : " + str(res))
```

**Output :**

> 原列表为:[('gfg '，4，' good ')，(' gfg '，2，' better ')，(' gfg '，1，' best ')，(' gfg '，3，' geeks')]
> Kth 索引的前 N 个元素为:[('gfg '，4，' good ')，(' gfg '，2，' better ')，(' gfg '，3，' geeks ')]