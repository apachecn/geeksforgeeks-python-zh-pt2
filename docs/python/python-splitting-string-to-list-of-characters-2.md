# Python |将字符串拆分为字符列表

> 原文:[https://www . geesforgeks . org/python-拆分-字符串到字符列表-2/](https://www.geeksforgeeks.org/python-splitting-string-to-list-of-characters-2/)

有时我们得到一个字符串，我们需要把它分解成单独的处理。这是一个非常常见的实用程序，在许多领域都有应用，无论是机器学习还是网络开发。人手不够可能会有帮助。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`list()`**
这是使用内置列表函数的内部实现来实现这一特定任务的最简单方法，该函数有助于将字符串分解为其字符组件。

```py
# Python3 code to demonstrate
# split string to character list
# using list()

# initializing string
test_string = 'GeeksforGeeks'

# printing the original string
print ("The original string is : " + str(test_string))

# using list()
# to split string to character list
res = list(test_string)

# printing result
print ("The splitted character's list is : " + str(res))
```

**Output :**

> 原始字符串为:GeeksforGeeks
> 拆分后的字符列表为:['G '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' G '，' e '，' e '，' k '，' s']

**方法 2:使用`map()`**
地图功能也可以用来执行这个特定的任务。映射函数需要以*无*值作为第一个参数执行该任务，以目标字符串作为最后一个参数。仅适用于 Python2。

```py
# Python code to demonstrate
# split string to character list
# using map()

# initializing string
test_string = 'GeeksforGeeks'

# printing the original string
print ("The original string is : " + str(test_string))

# using map()
# to split string to character list
res = list(map(None, test_string))

# printing result
print ("The splitted character's list is : " + str(res))
```

**Output :**

> 原始字符串为:GeeksforGeeks
> 拆分后的字符列表为:['G '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' G '，' e '，' e '，' k '，' s']