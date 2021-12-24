# Python 程序改变字典中的值

> 原文:[https://www . geeksforgeeks . org/python-程序更改字典中的值/](https://www.geeksforgeeks.org/python-program-to-change-values-in-a-dictionary/)

给定 Python 中的一个字典，任务是编写一个 Python 程序来更改其中一个键值对中的值。本文讨论了有效做到这一点的机制。

**示例:**

```
Input: {'hari': 1, 'dita': 2}
Output: {'hari': 1, 'dita': 4}

Input: {'hari': 1, 'dita': 2}
Output: {'hari': 3, 'dita': 5}
```

### 改变字典的价值

**方法 1**

在这种情况下，我们引用要更改的值的键，并为其提供一个新值。

**示例:**

## 蟒蛇 3

```
# declaring dictionary
dict = {'hari': 1, 'dita': 2}

# original dictionary
print("initial dictionary-", dict)

# changing the key value from  2 to 4
dict['dita'] = 4

# dictionary after update
print("dictionary after modification-", dict)
```

**输出:**

> 初始词典- {'hari': 1，' dita': 2}
> 
> 修改后的词典-{“Hari”:1，“dita”:4 }

**方法二:**

在这种方法中，我们使用 [zip()](https://www.geeksforgeeks.org/zip-in-python/) 函数，该函数聚合可迭代对象并将它们组合成元组形式。

**示例:**

## 蟒蛇 3

```
# declaring dictionary
dict1 = {'hari': 1, 'dita': 2}

# original dictionary
print("initial dictionary-", dict1)

# list of values which will replace the values of dict1
list1 = [3, 5]

# this preserves the keys and modifies the values
dict1 = dict(zip(list(dict1.keys()), list1))

# modified dictionary
print("dictionary after modification-", dict1)
```

**输出:**

> 初始词典-{“Hari”:1，“dita”:2 }
> 
> 修改后的字典- {'hari': 3，' dita': 5}