# Python–在列表中查找几何平均值的方法

> 原文:[https://www . geesforgeks . org/python-查找方法-列表中的几何平均值/](https://www.geeksforgeeks.org/python-ways-to-find-geometric-mean-in-list/)

在使用 Python 时，我们可能会遇到一个问题，即我们需要找到一个累积列表的几何平均值。这个问题在数据科学领域很常见。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环+公式**
处理这个问题的更简单的方式是使用计算几何平均值的公式，并使用循环短指针执行。这是解决这个问题最基本的方法。

```py
# Python3 code to demonstrate working of 
# Geometric Mean of List 
# using loop + formula 
import math

# initialize list 
test_list = [6, 7, 3, 9, 10, 15] 

# printing original list 
print("The original list is : " + str(test_list)) 

# Geometric Mean of List 
# using loop + formula 
temp = 1
for i in range(0, len(test_list)) : 
    temp = temp * test_list[i] 
temp2 = (float)(math.pow(temp, (1 / len(test_list)))) 
res = (float)(temp2) 

# printing result 
print("The geometric mean of list is : " + str(res)) 
```

**Output :**

```py
The original list is : [6, 7, 3, 9, 10, 15]
The geometric mean of list is : 7.443617568993922

```