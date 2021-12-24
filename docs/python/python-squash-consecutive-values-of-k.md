# Python–挤压连续的 K 值

> 原文:[https://www . geeksforgeeks . org/python-puck-continuous-values-of-k/](https://www.geeksforgeeks.org/python-squash-consecutive-values-of-k/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即需要删除特定元素的重复连续值。这类问题可以应用于许多领域，如竞争性编程和 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [4，5，5，4，3，3，5，5，5，6，5]，K = 3
> **输出** : [4，5，5，4，3，5，5，5，6，5]
> 
> **输入** : test_list = [1，1，1，1]，K = 1
> **输出** : [1]

**方法#1:使用`zip()` +产量**
以上功能的组合提供了解决这个问题的方法之一。在这种情况下，我们使用压缩当前和下一个元素列表来执行检查连续重复的任务，并使用 yield 来呈现条件的元素基础。

```
# Python3 code to demonstrate working of 
# Squash consecutive values of K
# Using zip() + yield

# helper function
def hlper_fnc(test_list, K):
    for sub1, sub2 in zip(test_list, test_list[1:]):
        if sub1 == sub2 == K:
            continue
        else:
            yield sub1
    yield sub2       

# initializing list
test_list = [4, 5, 5, 4, 3, 3, 5, 5, 5, 6, 5] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# Squash consecutive values of K
# Using zip() + yield
res = list(hlper_fnc(test_list, K))

# printing result 
print("List after filteration : " + str(res))
```

**Output :**

```
The original list is : [4, 5, 5, 4, 3, 3, 5, 5, 5, 6, 5]
List after filteration : [4, 5, 4, 3, 3, 5, 6, 5]

```

**方法 2:使用`yield + groupby()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 groupby()执行分组任务，以检查连续性，yield 用于返回有效元素。

```
# Python3 code to demonstrate working of 
# Squash consecutive values of K
# Using yield + groupby()
import itertools

# helper function
def hlper_fnc(test_list, K):
    for key, val in itertools.groupby(test_list):
        if key == K:
            yield key
        else:
            yield from val    

# initializing list
test_list = [4, 5, 5, 4, 3, 3, 5, 5, 5, 6, 5] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# Squash consecutive values of K
# Using yield + groupby()
res = list(hlper_fnc(test_list, K))

# printing result 
print("List after filteration : " + str(res))
```

**Output :**

```
The original list is : [4, 5, 5, 4, 3, 3, 5, 5, 5, 6, 5]
List after filteration : [4, 5, 4, 3, 3, 5, 6, 5]

```