# Python–唯一值乘法

> 原文:[https://www . geesforgeks . org/python-unique-values-乘法/](https://www.geeksforgeeks.org/python-unique-values-multiplication/)

本文着重于从包含可能重复的列表中获取唯一列表并执行其产品的操作之一。这种操作有大量的应用程序，因此它的知识很好。

**方法 1:朴素方法+循环**
在朴素方法中，我们只需遍历列表，在新列表中追加元素的第一次出现，并忽略该特定元素的所有其他出现。使用循环执行产品任务。

```py
# Python 3 code to demonstrate 
# Unique values Multiplication
# using naive methods + loop

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing list
test_list = [1, 3, 5, 6, 3, 5, 6, 1]
print ("The original list is : " + str(test_list))

# using naive method + loop
# Unique values Multiplication
# from list 
res = []
for i in test_list:
    if i not in res:
        res.append(i)
res = prod(res)

# printing list after product
print ("The unique elements product : " + str(res))
```

**Output :**

```py
The original list is : [1, 3, 5, 6, 3, 5, 6, 1]
The unique elements product : 90

```