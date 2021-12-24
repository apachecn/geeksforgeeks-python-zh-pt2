# Python |按后缀分隔列表元素

> 原文:[https://www . geesforgeks . org/python-按后缀分隔列表元素/](https://www.geeksforgeeks.org/python-segregate-list-elements-by-suffix/)

有时，我们需要用列表中每个字符串的最后一个字符来过滤列表。这种类型的任务在日常编程甚至在竞争性编程领域都有许多应用。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+ `endswith()`**

在这个方法中，我们使用遍历逻辑的列表理解和 endswith 方法来过滤掉所有以特定字母结尾的字符串。左边的字符串可以用来制作不同的列表。

```py
# Python3 code to demonstrate
# Segregating by Suffix
# Using list comprehension + endwith()

# initializing list
test_list = ['apple', 'oranges', 'mango', 'grapes']

# initializing end Suffix
end_letter = 's'

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + endwith()
# Segregating by Suffix
with_s = [x for x in test_list if x.endswith(end_letter)]
without_s = [x for x in test_list if x not in with_s]

# print result
print("The list without suffix s : " + str(without_s))
print("The list with suffix s : " + str(with_s))
```

**Output :**

```py
The original list : ['apple', 'oranges', 'mango', 'grapes']
The list without suffix s : ['apple', 'mango']
The list with suffix s : ['oranges', 'grapes']

```

**方法二:使用`filter()`+λ+`endwith()`+T3】**

可以使用 filter 函数执行此任务，该函数在内部执行与上述函数类似的任务，lambda 是构建逻辑的助手函数。

```py
# Python3 code to demonstrate
# Segregating by Suffix
# Using filter() + endwith() + lambda

# initializing list
test_list = ['apple', 'oranges', 'mango', 'grapes']

# initializing end Suffix
end_letter = 's'

# printing original list
print("The original list : " + str(test_list))

# using filter() + endwith() + lambda
# Segregating by Suffix
with_s = list(filter(lambda x: x.endswith(end_letter), test_list))
without_s = list(filter(lambda x: not x.endswith(end_letter), test_list))

# print result
print("The list without suffix s : " + str(without_s))
print("The list with suffix s : " + str(with_s))
```

**Output :**

```py
The original list : ['apple', 'oranges', 'mango', 'grapes']
The list without suffix s : ['apple', 'mango']
The list with suffix s : ['oranges', 'grapes']

```