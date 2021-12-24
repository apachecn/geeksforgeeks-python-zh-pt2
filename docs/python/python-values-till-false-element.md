# Python |值直到假元素

> 原文:[https://www . geesforgeks . org/python-values-till-false-element/](https://www.geeksforgeeks.org/python-values-till-false-element/)

很多时候，我们需要找到第一个出现的假数字来开始处理。这主要是在机器学习领域中的用例，其中我们需要处理除了无或 0 值之外的数据。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`next() + enumerate()`**
下一个函数可用于遍历列表，并与其一起枚举，检查列表中的数字是否为 False 元素，并返回 False 值(即零值)之前的 true 数。

```
# Python3 code to demonstrate 
# Values till False element
# using next() and enumerate()

# initializing list 
test_list = [ 1, 5, 0, 0, 6]

# printing original list
print ("The original list is : " + str(test_list))

# Values till False element
# using next() and enumerate()
res = next((i for i, j in enumerate(test_list) if not j), None)

# printing result
print ("The values till first False value : " + str(res))
```

**Output :**

```
The original list is : [1, 5, 0, 0, 6]
The values till first False value : 2

```