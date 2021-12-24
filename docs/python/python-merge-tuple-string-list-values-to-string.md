# Python |将元组字符串列表值合并到字符串中

> 原文:[https://www . geesforgeks . org/python-merge-tuple-string-list-values-to-string/](https://www.geeksforgeeks.org/python-merge-tuple-string-list-values-to-string/)

有时，在处理记录时，我们可能会遇到这样的问题:记录的任何元素都可以是字符串类型，但被错误地处理为字符列表。在处理大量数据时，这可能是一个问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `join()`**
上述功能的组合可用于实现上述任务的求解。在这种情况下，我们使用列表理解获得字符列表，转换任务由`join()`执行。

```py
# Python3 code to demonstrate working of
# Merge Tuple String List values to String
# using list comprehension + join()

# initialize list
test_list = [(['g', 'f', 'g'], 1), (['i', 's'], 2), (['b', 'e', 's', 't'], 3)]

# printing original list
print("The original list : " + str(test_list))

# Merge Tuple String List values to String
# using list comprehension + join()
res =  [''.join(i) for i, j in test_list]

# printing result
print("The joined character list tuple element to string is : " + str(res))
```

**Output :**

> 原始列表:[(['g '，' f '，' g']，1)、(['i '，' s']，2)、(['b '，' e '，' s '，' t']，3)]
> 字符串的连接字符列表元组元素为:['gfg '，' is '，' best']