# Python |从元组中移除重复项

> 原文:[https://www . geesforgeks . org/python-从元组中移除重复项/](https://www.geeksforgeeks.org/python-removing-duplicates-from-tuple/)

很多时候，在使用 Python 元组时，我们会遇到删除重复项的问题。这是一个非常常见的问题，可以出现在任何形式的编程设置中，无论是常规编程还是 web 开发。让我们讨论执行这项任务的某些方法。

**方法一:使用`set() + tuple()`**
这是去除重复项最直接的方法。在这种情况下，我们将元组转换为集合，移除重复项，然后使用`tuple()`将其再次转换回来。

```
# Python3 code to demonstrate working of
# Removing duplicates from tuple 
# using tuple() + set()

# initialize tuple
test_tup = (1, 3, 5, 2, 3, 5, 1, 1, 3)

# printing original tuple 
print("The original tuple is : " + str(test_tup))

# Removing duplicates from tuple 
# using tuple() + set()
res = tuple(set(test_tup))

# printing result
print("The tuple after removing duplicates : " + str(res))
```

**Output :**

```
The original tuple is : (1, 3, 5, 2, 3, 5, 1, 1, 3)
The tuple after removing duplicates : (1, 2, 3, 5)

```