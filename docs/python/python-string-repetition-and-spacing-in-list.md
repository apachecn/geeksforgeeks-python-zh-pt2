# Python–列表中的字符串重复和间距

> 原文:[https://www . geesforgeks . org/python-string-repeat-and-spacing-in-list/](https://www.geeksforgeeks.org/python-string-repetition-and-spacing-in-list/)

有时在使用 Python 时，我们会遇到一个问题，即我们需要重复列表中的每个字符串，并且还需要为每个事件附加一个 deliminator。这种问题可能发生在日常编程中。让我们讨论执行这项任务的某些方法。
**方法#1:使用循环**
这个任务可以使用循环以蛮力的方式执行。在这种情况下，我们迭代列表，并在迭代时使用合适的运算符执行字符串加法和乘法。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# String Repetition and spacing in List
# Using loop

# initializing list
test_list = ['gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# initializing delim
delim = '-'

# initializing K
K = 3

# String Repetition and spacing in List
# Using loop
res = []
for sub in test_list:
    res.append((sub + delim) * K)

# printing result
print("List after performing operations : " + str(res))
```

**Output : **

```
The original list is : ['gfg', 'is', 'best']
List after performing operations : ['gfg-gfg-gfg-', 'is-is-is-', 'best-best-best-']
```

**方法 2:使用 join() +列表理解**
以上功能的组合也可以用来执行此任务。在本文中，我们使用 join()执行附加 delim 的任务，列表理解执行重复的任务。避免尾随 delim。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# String Repetition and spacing in List
# Using join() + list comprehension

# initializing list
test_list = ['gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# initializing delim
delim = '-'

# initializing K
K = 3

# String Repetition and spacing in List
# Using join() + list comprehension
res = []
for sub in test_list:
    res.append(delim.join([sub for _ in range(K)]))

# printing result
print("List after performing operations : " + str(res))
```

**Output : **

```
The original list is : ['gfg', 'is', 'best']
List after performing operations : ['gfg-gfg-gfg', 'is-is-is', 'best-best-best']
```