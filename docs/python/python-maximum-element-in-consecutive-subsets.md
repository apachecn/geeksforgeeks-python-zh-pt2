# Python–连续子集中的最大元素

> 原文:[https://www . geesforgeks . org/python-最大连续元素子集/](https://www.geeksforgeeks.org/python-maximum-element-in-consecutive-subsets/)

编程领域的一些经典问题来自不同的类别，其中之一就是求子集的最大值。当我们需要计算最大值并存储连续的组最大值时，这个特殊的问题也很常见。让我们用 python 语言尝试不同的方法来解决这个问题。

**方法#1:使用列表理解+ max()**
可以使用列表理解来执行这个特定的任务，以过滤掉连续的组，并且可以使用 max 函数来获得过滤后的解的最大值。

```
# Python3 code to demonstrate
# Maximum element in consecutive subsets
# using list comprehension + max()

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + max()
# Maximum element in consecutive subsets
res = [ max(test_list[x : x + 3]) 
        for x in range(0, len(test_list), 3)]

# printing result
print("The grouped maximized list is : " + str(res))
```

**Output :**

```
The original list : [4, 7, 8, 10, 12, 15, 13, 17, 14]
The grouped maximized list is : [8, 15, 17]

```