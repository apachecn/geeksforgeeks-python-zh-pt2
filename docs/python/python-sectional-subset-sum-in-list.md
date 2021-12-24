# Python |列表中的截面子集和

> 原文:[https://www . geesforgeks . org/python-secular-subset-sum-in-list/](https://www.geeksforgeeks.org/python-sectional-subset-sum-in-list/)

编程领域的一些经典问题来自不同的类别，其中之一就是求子集的和。当我们需要累加总和并存储连续的组总和时，这个特殊的问题也很常见。让我们用 python 语言尝试不同的方法来解决这个问题。

**方法#1:使用列表理解+ `sum()`**
可以使用列表理解来执行这个特定的任务，以过滤出连续的组，并且可以使用求和函数来获得过滤后的解的总和。

```
# Python3 code to demonstrate
# Sectional subset sum in list 
# using list comprehension + sum()

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + sum()
# Sectional subset sum in list 
res = [ sum(test_list[x : x + 3]) 
       for x in range(0, len(test_list), 3)]

# printing result
print("The grouped summation list is : " + str(res))
```

**Output :**

```
The original list : [4, 7, 8, 10, 12, 15, 13, 17, 14]
The grouped summation list is : [19, 37, 44]

```