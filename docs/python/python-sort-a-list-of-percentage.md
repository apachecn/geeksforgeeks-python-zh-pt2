# Python |排序百分比列表

> 原文:[https://www . geesforgeks . org/python-sort-a-list-of-percent/](https://www.geeksforgeeks.org/python-sort-a-list-of-percentage/)

给定一个百分比列表，编写一个 Python 程序以升序对给定列表进行排序。

让我们看看完成任务的不同方法。

**代码#1:** 在字符串中切“%”，转换成浮点数。

```py
# Python code to sort list of percentage 

# List initialization
Input =['2.5 %', '6.4 %', '91.6 %', '11.5 %']

# removing % and converting to float
# then apply sort function
Input.sort(key = lambda x: float(x[:-1]))

# printing output
print(Input)
```

**Output:**

```py
['2.5 %', '6.4 %', '11.5 %', '91.6 %']

```

**代码#2:**

```py
# Python code to sort list of percentage 

# List initialization
Input =['2.5 %', '6.4 %', '91.6 %', '11.5 %']

# Temporary list initialization
temp = []

# removing % sign
for key in Input:
    temp.append((key[:-1]))

# sorting list of float
temp = sorted(temp, key = float)

# Output list initialization
output = []

# Adding percentage sign
for key in temp:
    output.append(key + '%')

# printing output
print(output)
```

**Output:**

```py
['2.5 %', '6.4 %', '11.5 %', '91.6 %']

```