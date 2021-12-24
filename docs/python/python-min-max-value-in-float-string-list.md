# Python |浮点字符串列表中的最小值/最大值

> 原文:[https://www . geesforgeks . org/python-min-max-value-in-float-string-list/](https://www.geeksforgeeks.org/python-min-max-value-in-float-string-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要在列表中找到最小值/最大值。但是有时候，我们没有自然数，只有字符串格式的浮点数。无论是在网络开发领域还是在数据科学领域，在处理数据时都会出现这个问题。让我们讨论一下解决这个问题的方法。
**方法:使用 min()/max() + float()**
这个问题可以通过使用 min 或 max 函数来解决，在该函数中，我们首先将字符串转换为 float，然后在各自的 min/max 函数中的函数中传递这个逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Min / Max value in float string list
# using min()/max() + float() + generator

# initialize lists
test_list = ['4.5', '7.8', '9.8', '10.3']

# printing original list
print("The original list is : " + str(test_list))

# Min / Max value in float string list
# using min()/max() +float + lambda function
res_min = min(test_list,key=lambda x:float(x))
res_max = max(test_list,key=lambda x:float(x))

# printing result
print("The min value of list : " + str(res_min))
print("The max value of list : " + str(res_max))
```

**Output**

```py
The original list is : ['4.5', '7.8', '9.8', '10.3']
The min value of list : 4.5
The max value of list : 10.3

```