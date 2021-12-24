# Python |索引处的出现百分比

> 原文:[https://www . geeksforgeeks . org/python-索引出现百分比/](https://www.geeksforgeeks.org/python-percentage-occurrence-at-index/)

有时在处理统计数据时，我们可能会遇到这样一个特殊的问题，即我们需要找到列表中特定索引处元素出现的百分比。让我们讨论一下实现这一点的某些方法。

**方法#1:使用循环+列表理解**
我们可以对每个列表索引使用循环来执行这个特定的任务，为此，我们可以使用列表理解逻辑来计算元素的出现百分比。

```
# Python3 code to demonstrate
# index percentage calculation of element
# using loop + list comprehension

# initializing test list
test_list = [[3, 4, 5], [2, 4, 6], [3, 5, 4]]

# printing original list 
print("The original list : " + str(test_list))

# using loop + list comprehension
# index percentage calculation of element
res = []
for i in range(len(test_list[1])):
    res.append(len([j[i] for j in test_list if j[i]== 4 ])/len(test_list))

# print result
print("The percentage of 4 each index is : " + str(res))
```

**Output :**

```
The original list : [[3, 4, 5], [2, 4, 6], [3, 5, 4]]
The percentage of 4 each index is : [0.0, 0.6666666666666666, 0.3333333333333333]

```