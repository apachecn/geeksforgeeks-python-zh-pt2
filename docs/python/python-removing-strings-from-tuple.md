# Python |从元组中移除字符串

> 原文:[https://www . geesforgeks . org/python-从元组中移除字符串/](https://www.geeksforgeeks.org/python-removing-strings-from-tuple/)

有时我们会遇到这样的问题:我们以元组的形式接收数据，我们只想从中获得数字，并希望删除其中的所有字符串。这在网络开发和机器学习中也很有用。让我们讨论一下完成这项特殊任务的某些方法。

**方法一:使用列表理解+ `type()`**

以上两个函数的组合可以用来解决这个特殊的问题。列表理解完成了修改后的列表的重建任务，类型函数帮助我们过滤字符串。

```py
# Python3 code to demonstrate
# Remove string from tuples
# using list comprehension + type()

# initializing list
test_list = [('Geeks', 1, 2), ('for', 4, 'Geeks'), (45, 'good')]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + type()
# Remove string from tuples
res = [tuple([j for j in i if type(j) != str])
                           for i in test_list]

# print result
print("The list after string removal is : " + str(res))
```

**Output :**

```py
The original list : [('Geeks', 1, 2), ('for', 4, 'Geeks'), (45, 'good')]
The list after string removal is : [(1, 2), (4, ), (45, )]

```

**方法 2:使用列表理解+ `isinstance()`**

这几乎是执行这个特定任务的类似方法，但是这里的变化只是使用 isinstance 函数来检查字符串数据类型，其余的公式仍然基本相似。

```py
# Python3 code to demonstrate
# Remove string from tuples
# using list comprehension + isinstance()

# initializing list
test_list = [('Geeks', 1, 2), ('for', 4, 'Geeks'), (45, 'good')]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + isinstance()
# Remove string from tuples
res = [tuple(j for j in i if not isinstance(j, str))
                                 for i in test_list]

# print result
print("The list after string removal is : " + str(res))
```

**Output :**

```py
The original list : [('Geeks', 1, 2), ('for', 4, 'Geeks'), (45, 'good')]
The list after string removal is : [(1, 2), (4, ), (45, )]

```