# Python |浮点值列表排序方式

> 原文:[https://www . geesforgeks . org/python-排序方式-浮点值列表/](https://www.geeksforgeeks.org/python-ways-to-sort-list-of-float-values/)

给定一个浮点值列表，编写一个 Python 程序对列表进行排序。

**示例:**

```
Input: list = ['1.2', '.8', '19.8', '2.7', '99.8', '80.7']
Output: ['.8', '1.2', '2.7', '19.8', '80.7', '99.8']

Input: list = [12.8, .178, 1.8, 782.7, 99.8, 8.7]
Output: [0.178, 1.8, 8.7, 12.8, 99.8, 782.7]

```

让我们讨论解决这个问题的不同方法。

**方法#1:使用λ**

```
# Python code to sort list of decimal values

# List initialization
Input =  [12.8, .178, 1.8, 782.7, 99.8, 8.7]

# Using sorted and lambda
Output = sorted(Input, key = lambda x:float(x))

# Printing output
print(Output)
```

**Output:**

```
[0.178, 1.8, 8.7, 12.8, 99.8, 782.7]

```

**方法 2:使用排序后的**

```
# Python code to sort list of decimal values

# List initialization
Input =  [12.8, .178, 1.8, 782.7, 99.8, 8.7]

# Using sorted + key
Output = sorted(Input, key = float)

# Printing output
print(Output)
```

**Output:**

```
[0.178, 1.8, 8.7, 12.8, 99.8, 782.7]

```

**方法 3:使用排序**

```
# Python code to sort list of decimal values

# List initialization
Input =  [12.8, .178, 1.8, 782.7, 99.8, 8.7]

# Using sort + key
Input.sort(key = float)

# Printing output
print(Input)
```

**Output:**

```
[0.178, 1.8, 8.7, 12.8, 99.8, 782.7]

```