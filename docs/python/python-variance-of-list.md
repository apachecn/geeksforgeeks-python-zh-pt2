# Python |列表差异

> 原文:[https://www.geeksforgeeks.org/python-variance-of-list/](https://www.geeksforgeeks.org/python-variance-of-list/)

在使用 Python 时，我们可能会遇到一个问题，即我们需要找到一个累积列表的方差。这个问题在数据科学领域很常见。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环+公式**
处理这个问题的更简单的方式是使用公式来寻找方差，并使用循环短手来执行。这是解决这个问题最基本的方法。

```
# Python3 code to demonstrate working of
# Variance of List
# using loop + formula

# initialize list
test_list = [6, 7, 3, 9, 10, 15]

# printing original list
print("The original list is : " + str(test_list))

# Variance of List
# using loop + formula
mean = sum(test_list) / len(test_list)
res = sum((i - mean) ** 2 for i in test_list) / len(test_list)

# printing result
print("The variance of list is : " + str(res))
```

**Output :**

```
The original list is : [6, 7, 3, 9, 10, 15]
The variance of list is : 13.888888888888891

```