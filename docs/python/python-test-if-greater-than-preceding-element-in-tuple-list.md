# Python–测试是否大于元组列表中的前一个元素

> 原文:[https://www . geesforgeks . org/python-test-if-before-before-in-element-tuple-list/](https://www.geeksforgeeks.org/python-test-if-greater-than-preceding-element-in-tuple-list/)

给定元组列表，检查元组列表中每个元素的前一个元素是否小于当前元素。

> **输入** : test_list = [(5，1)，(4，9)，(3，5)]
> **输出** : [[False，False]，[False，True]，[False，True]]
> **解释**:第一个元素总是为 False，检查下一个元素是否有更大的值。
> 
> **输入** : test_list = [(1，8)，(2，2)，(3，6)，(4，2)]
> **输出**:[[假，真]，[假，假]，[假，真]，[假，假]]
> **说明** : 8 和 6 是以上情况中较大的情况，因此为真。

**方法#1:使用列表理解+ `enumerate()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用一个线性列表理解来执行检查更大值的任务，并且 enumerate()用于在嵌套迭代时处理索引。

```
# Python3 code to demonstrate working of 
# Test if greater than preceding element in Tuple List
# Using list comprehension + enumerate()

# initializing list
test_list = [(3, 5, 1), (7, 4, 9), (1, 3, 5)]

# printing original list 
print("The original list : " + str(test_list))

# Test if greater than preceding element in Tuple List
# Indices checked using enumerate() and True and false 
# values assigned in list comprehension
res = [[True if idx > 0 and j > i[idx - 1] else False 
        for idx, j in enumerate(i)] for i in test_list]

# printing result 
print("Filtered values : " + str(res))
```

**Output :**

```
The original list : [(3, 5, 1), (7, 4, 9), (1, 3, 5)]
Filtered values : [[False, True, False], [False, False, True], [False, True, True]]

```

**方法二:使用`tee() + zip()` +列表理解**
这是可以执行这个任务的方式之一。在本例中，我们使用 tee()提取元素并以大小= 2 的元组呈现它们。列表理解和 zip()用于构建期望的结果。

```
# Python3 code to demonstrate working of 
# Test if greater than preceding element in Tuple List
# Using tee() + zip() + list comprehension
from itertools import tee

# helper function
def pair(test_list):

    # pairing elements in 2 sized tuple
    x, y = tee(test_list)
    next(y, None)
    return zip(x, y)

# initializing list
test_list = [(3, 5, 1), (7, 4, 9), (1, 3, 5)]

# printing original list 
print("The original list : " + str(test_list))

# Test if greater than preceding element in Tuple List
# Using tee() + zip() + list comprehension
res = []
for sub in test_list:

    # appending result by checking with Dual Pairs
    res.append(tuple((False, )) + tuple([x < y for x, y in pair(sub)]))

# printing result 
print("Filtered values : " + str(res))
```

**Output :**

```
The original list : [(3, 5, 1), (7, 4, 9), (1, 3, 5)]
Filtered values : [[False, True, False], [False, False, True], [False, True, True]]

```