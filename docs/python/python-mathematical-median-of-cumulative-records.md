# Python |累计记录的数学中位数

> 原文:[https://www . geesforgeks . org/python-数学-累计记录中位数/](https://www.geeksforgeeks.org/python-mathematical-median-of-cumulative-records/)

有时，在使用 Python 元组列表时，我们可能会遇到一个问题，即我们需要找到列表中元组值的中值。这个问题在包括数学在内的许多领域都有可能应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `"~" operator`**
该任务可以使用上述功能的组合以暴力方式执行。在这种情况下，我们对列表和进行排序，通过使用“~”运算符的属性来执行否定，我们在扁平化后从前面和后面访问列表，执行找到中值所需的计算。

```
# Python3 code to demonstrate working of 
# Mathematical Median of Cumulative Records
# Using loop + "~" operator 

# initializing list 
test_list = [(1, 4, 5), (7, 8), (2, 4, 10)]

# printing list 
print("The original list : " + str(test_list)) 

# Mathematical Median of Cumulative Records 
# Using loop + "~" operator 
res = []
for sub in test_list :
  for ele in sub :
    res.append(ele)
res.sort() 
mid = len(res) // 2
res = (res[mid] + res[~mid]) / 2

# Printing result 
print("Median of Records is : " + str(res)) 
```

**Output :**

```
The original list : [(1, 4, 5), (7, 8), (2, 4, 10)]
Median of Records is : 4.5

```