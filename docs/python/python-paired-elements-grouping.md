# Python–成对元素分组

> 原文:[https://www . geesforgeks . org/python-成对-元素-分组/](https://www.geeksforgeeks.org/python-paired-elements-grouping/)

有时，在使用 Python 记录时，我们可能会遇到这样的问题，即我们将元组列表作为数据，并且我们希望将形成链的所有元素分组，即它们是彼此的间接对或者是连接的组件。这种问题可能发生在竞争编程等领域。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_list = [(1，3)，(4，5)]
> **输出** : []
> 
> **输入** : test_list = [(1，3)，(3，5)]
> **输出** : [{1，3，5}]

**方法:使用 loop + `set() + intersection()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们对所有元素进行迭代，然后对嵌套循环中在此之后出现的所有元素进行迭代。执行元素的交集，如果发现任何元素相似，即大小> = 0，则元组被合并到相似链中。

```
# Python3 code to demonstrate working of 
# Paired elements grouping
# Using loop + set() + intersection()

# initializing list
test_list = [(1, 3), (4, 5), (1, 7), (3, 4), (7, 8)]

# printing original list
print("The original list is : " + str(test_list))

# Paired elements grouping
# Using loop + set() + intersection()
res = []
for sub in test_list:
    idx = test_list.index(sub)
    sub_list = test_list[idx + 1:]
    if idx <= len(test_list) - 2:
        for ele in sub_list:
            intrsct = set(sub).intersection(set(ele))
            if len(intrsct) > 0:
                res.append(set(sub + ele))

# printing result 
print("The grouped list : " + str(res)) 
```

**Output :**

```
The original list is : [(1, 3), (4, 5), (1, 7), (3, 4), (7, 8)]
The grouped list : [{1, 3, 7}, {1, 3, 4}, {3, 4, 5}, {8, 1, 7}]

```