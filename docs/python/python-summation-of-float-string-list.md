# Python–浮点字符串列表的求和

> 原文:[https://www . geeksforgeeks . org/python-float-string-list 求和/](https://www.geeksforgeeks.org/python-summation-of-float-string-list/)

有时候，在使用 Python 列表时，我们会遇到一个问题，需要在列表中找到求和。但是有时候，我们没有自然数，只有字符串格式的浮点数。无论是在网络开发领域还是在数据科学领域，在处理数据时都会出现这个问题。让我们讨论一下解决这个问题的方法。

**方法#1:使用`sum() + float()` +生成器**
这个问题可以使用和函数来解决，在和函数中，我们首先将字符串转换为 float，然后将这个逻辑传递给各自和函数中的函数。

```
# Python3 code to demonstrate working of
# Summation of float string list
# using sum() + float() + generator

# initialize lists
test_list = ['4.5', '7.8', '9.8', '10.3']

# printing original list
print("The original list is : " + str(test_list))

# Summation of float string list
# using sum() + float() + generator
res_sum = sum(float(sub) for sub in test_list)

# printing result
print("The summation of float string list : " + str(res_sum))
```

**Output :**

```
The original list is : ['4.5', '7.8', '9.8', '10.3']
The summation of float string list : 32.400000000000006

```