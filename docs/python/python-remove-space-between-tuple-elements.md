# Python–删除元组元素之间的空间

> 原文:[https://www . geesforgeks . org/python-remove-tuple-elements 之间的空间/](https://www.geeksforgeeks.org/python-remove-space-between-tuple-elements/)

有时，在使用元组时，我们可能会遇到这样的问题，即我们需要打印元组，逗号和下一个元素之间没有空格，按照惯例，这是存在的。这个问题可以用在日常和学校的编程中。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (7，6，8)
> **输出** : (7，6，8)
> **输入** : test_tuple = (6，8)
> **输出** : (6，8)

**方法#1:使用 str() + replace()**
以上函数的组合可以用来解决这个问题。在这种情况下，我们通过用空白空间替换来执行移除额外空间的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove space between tuple elements
# Using replace() + str()

# initializing tuples
test_tuple = (4, 5, 7, 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Remove space between tuple elements
# Using replace() + str()
res = str(test_tuple).replace(' ', '')

# printing result
print("The tuple after space removal : " + str(res))
```

**Output : **

```py
The original tuple : (4, 5, 7, 6, 8)
The tuple after space removal : (4, 5, 7, 6, 8)
```

**方法 2:使用 join() + map()**
另一种方法解决这个问题。在本文中，我们使用 join()通过外部连接每个元素来执行空间移除任务，并使用 map()将字符串转换的逻辑扩展到每个元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove space between tuple elements
# Using join() + map()

# initializing tuples
test_tuple = (4, 5, 7, 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Remove space between tuple elements
# Using join() + map()
res = "(" + ", ".join(map(str, test_tuple)) + ")"

# printing result
print("The tuple after space removal : " + str(res))
```

**Output : **

```py
The original tuple : (4, 5, 7, 6, 8)
The tuple after space removal : (4, 5, 7, 6, 8)
```