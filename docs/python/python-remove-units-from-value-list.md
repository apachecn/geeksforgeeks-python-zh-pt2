# Python–从值列表中删除单位

> 原文:[https://www . geesforgeks . org/python-从值列表中移除单位/](https://www.geeksforgeeks.org/python-remove-units-from-value-list/)

有时，在使用 Python 值列表时，我们可能会遇到一个问题，即需要移除值中的单元。这个问题在日常编程和数据预处理中有直接的应用。让我们讨论执行这项任务的某些方法。

> **输入**:test _ list =【“54cm”、“23 cm”、“12cm”、“19 cm”】，单位=【cm】
> **输出**:【‘54’、‘23’、‘12’、‘19’】
> **输入**:test _ list =【“54cm”】，单位=【cm】
> **输出**:【‘54’】

**方法#1:使用 regex() +列表理解**
这些函数的组合可以用来解决这个问题。在这种情况下，我们通过使用正则表达式只提取数字，并移除剩余的字符串单元来实现。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Units from Value List
# Using list comprehension + regex()
import re

# initializing list
test_list = ["54 kg", "23 kg", "12kg", "19  kg"]

# printing original list
print("The original list is : " + str(test_list))

# initializing unit
unit = "kg"

# Remove Units from Value List
# Using list comprehension + regex()
res = re.findall('\d+', ' '.join(test_list))

# printing result
print("List after unit removal : " + str(res))
```

**Output : **

```py
The original list is : ['54 kg', '23 kg', '12kg', '19  kg']
List after unit removal : ['54', '23', '12', '19']
```

**方法 2:使用 replace() + strip() +列表理解**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 replace()执行用空字符串替换单元的任务，并使用 strip()处理杂散空间。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Units from Value List
# Using replace() + strip() + list comprehension
import re

# initializing list
test_list = ["54 kg", "23 kg", "12kg", "19  kg"]

# printing original list
print("The original list is : " + str(test_list))

# initializing unit
unit = "kg"

# Remove Units from Value List
# Using replace() + strip() + list comprehension
res = [sub.replace(unit, "").strip() for sub in test_list]

# printing result
print("List after unit removal : " + str(res))
```

**Output : **

```py
The original list is : ['54 kg', '23 kg', '12kg', '19  kg']
List after unit removal : ['54', '23', '12', '19']
```