# Python–独特元素的总和

> 原文:[https://www . geesforgeks . org/python-唯一元素求和/](https://www.geeksforgeeks.org/python-summation-of-unique-elements/)

本文重点介绍从包含可能重复项的列表中获取唯一列表并执行其求和的操作之一。这种操作有大量的应用程序，因此它的知识很好。

**方法 1:朴素方法+ sum()**
在朴素方法中，我们只需遍历列表，在新列表中追加元素的第一次出现，并忽略该特定元素的所有其他出现。求和的任务是使用 sum()执行的。

```
# Python 3 code to demonstrate 
# Summation of Unique elements
# using naive methods + sum()

# initializing list
test_list = [1, 3, 5, 6, 3, 5, 6, 1]
print ("The original list is : " + str(test_list))

# using naive method + sum()
# Summation of Unique elements
# from list 
res = []
for i in test_list:
    if i not in res:
        res.append(i)
res = sum(res)

# printing list after removal 
print ("The unique elements summation : " + str(res))
```

**Output :**

```
The original list is : [1, 3, 5, 6, 3, 5, 6, 1]
The unique elements summation : 15

```