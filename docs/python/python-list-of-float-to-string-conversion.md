# Python |浮点到字符串转换列表

> 原文:[https://www . geesforgeks . org/python-list-float-to-string-conversion/](https://www.geeksforgeeks.org/python-list-of-float-to-string-conversion/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们必须将列表元素转换为字符串。这在积分列表的情况下更容易，因为它们可以很容易地与`join()`连接，并且可以显示它们的内容。但是浮动的情况不同，在它的值中有额外的不需要的空格会导致它的不成功。让我们讨论一下处理这种错误情况的方法。

**方法#1:使用列表理解+ `join() + str()`**
该任务可以使用以上功能的组合来执行。在这种情况下，我们首先将列表中的每个元素(即浮点数)转换为字符串，然后使用`join()`连接结果字符串。

```py
# Python3 code to demonstrate working of
# List of float to string conversion
# using list comprehension + str() + join()

# initialize list
test_list = [5.8, 9.6, 10.2, 45.3, 6.0]

# printing original list
print("The original list is : " + str(test_list))

# List of float to string conversion
# using list comprehension + str() + join()
res = " ".join([str(i) for i in test_list])

# printing result
print("Conversion of float list to string : " + str(res))
```

**Output :**

```py
The original list is : [5.8, 9.6, 10.2, 45.3, 6.0]
Conversion of float list to string : 5.8 9.6 10.2 45.3 6.0

```