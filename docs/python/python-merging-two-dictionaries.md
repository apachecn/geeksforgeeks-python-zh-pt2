# Python |合并两本词典

> 原文:[https://www . geesforgeks . org/python-合并-两个-字典/](https://www.geeksforgeeks.org/python-merging-two-dictionaries/)

通过使用 Python 中的各种函数和构造函数，有多种方法可以合并字典。在本文中，我们将讨论几种合并词典的方法。

### **使用方法 update()**

通过使用 Python 中的 update()方法，一个列表可以合并到另一个列表中。但是在这种情况下，第二个列表被合并到第一个列表中，并且没有创建新的列表。它返回*无*。

**示例:**

## 蟒蛇 3

```py
# Python code to merge dict using update() method
def Merge(dict1, dict2):
    return(dict2.update(dict1))

# Driver code
dict1 = {'a': 10, 'b': 8}
dict2 = {'d': 6, 'c': 4}

# This return None
print(Merge(dict1, dict2))

# changes made in dict2
print(dict2)
```

**输出:**

```py
None
{'c': 4, 'a': 10, 'b': 8, 'd': 6}

```

### **使用** [****在 Python 中**](https://www.geeksforgeeks.org/args-kwargs-python/)

这通常被认为是 Python 中的一个技巧，其中一个表达式用于合并两个字典，并存储在第三个字典中。单一的表情就是**。这并不影响其他两本词典。**意味着一个论点就是一本字典。使用* *[双星]是一种快捷方式，允许您直接使用字典向函数传递多个参数。更多信息请参考 Python 中的[* * kwargs](https://www.geeksforgeeks.org/args-kwargs-python/)。利用这一点，我们首先将第一个字典的所有元素传递给第三个字典，然后将第二个字典传递给第三个字典。这将替换第一个字典的重复键。

**示例:**

## 蟒蛇 3

```py
# Python code to merge dict using a single
# expression
def Merge(dict1, dict2):
    res = {**dict1, **dict2}
    return res

# Driver code
dict1 = {'a': 10, 'b': 8}
dict2 = {'d': 6, 'c': 4}
dict3 = Merge(dict1, dict2)
print(dict3)
```

**输出:**

```py
{'b': 8, 'a': 10, 'c': 4, 'd': 6}

```

### 在 Python 3.9 中使用|

在 python 的最新更新中，我们现在可以使用“|”运算符来合并两个字典。合并词典是一种非常方便的方法。

**示例:**

## 蟒蛇 3

```py
# code
# Python code to merge dict using a single 
# expression
def Merge(dict1, dict2):
    res = dict1 | dict2
    return res

# Driver code
dict1 = {'x': 10, 'y': 8}
dict2 = {'a': 6, 'b': 4}
dict3 = Merge(dict1, dict2)
print(dict3)

# This code is contributed by virentanti16
```

**输出:**

```py
{'x': 10, 'a': 6,  'b': 4, 'y': 8}

```