# Python |给定列表元素的格式化方式

> 原文:[https://www . geesforgeks . org/python-格式化给定列表元素的方法/](https://www.geeksforgeeks.org/python-ways-to-format-elements-of-given-list/)

给定一个浮点值列表，任务是将所有浮点值截断为 2 位小数。让我们看看完成任务的不同方法。
**方法一:使用列表理解**

## 蟒蛇 3

```py
# Python code to truncate float
# values to 2-decimal digits.

# List initialization
Input = [100.7689454, 17.232999, 60.98867, 300.83748789]

# Using list comprehension
Output = ["%.2f" % elem for elem in Input]

# Printing output
print(Output)
```

**Output:** 

```py
['100.77', '17.23', '60.99', '300.84']
```

**方法 2:使用地图**

## 蟒蛇 3

```py
# Python code to truncate float
# values to 2 decimal digits.

# List initialization
Input = [100.7689454, 17.232999, 60.98867, 300.83748789]

# Using map
Output = map(lambda n: "%.2f" % n, Input)

# Converting to list
Output = list(Output)

# Print output
print(Output)
```

**Output:** 

```py
['100.77', '17.23', '60.99', '300.84']
```

**方法三:使用格式**

## 蟒蛇 3

```py
# Python code to truncate float
# values to 2 decimal digits.

# List initialization
Input = [100.7689454, 17.232999, 60.98867, 300.83748789]

# Using format
Output = ['{:.2f}'.format(elem) for elem in Input]

# Print output
print(Output)
```

**Output:** 

```py
['100.77', '17.23', '60.99', '300.84']
```

**方法#4:使用迭代**

## 蟒蛇 3

```py
# Python code to truncate float
# values to 2 decimal digits.

# List initialization
Input = [100.7689454, 17.232999, 60.98867, 300.83748789]

# Output list initialization
Output = []

# Iterating
for elem in Input:
    Output.append("%.2f" % elem)

# Printing output
print(Output)
```

**Output:** 

```py
['100.77', '17.23', '60.99', '300.84']
```