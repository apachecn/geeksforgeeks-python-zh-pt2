# Python–另一个

中每个列表元素出现的总和

> 原文:[https://www . geesforgeks . org/python-每个列表元素的总和-在另一个列表中出现/](https://www.geeksforgeeks.org/python-sum-of-each-list-element-occurrence-in-another/)

有时，在使用 Python 时，我们会遇到一个问题，需要在另一个元素中出现一个元素。但是作为一个修改，我们可能会遇到一个问题，我们需要计算一个列表的所有元素在另一个列表中的出现次数。让我们讨论执行这项任务的某些方法。

**方法#1:使用嵌套循环**
这是执行该任务的方法之一。这是一种可以执行这项任务的暴力方式。在这种情况下，我们迭代一个列表，然后目标列表，如果元素匹配，我们增加计数器。

```py
# Python3 code to demonstrate 
# Sum of each List element occurrence in another
# using nested loops

# Initializing lists
test_list1 = [1, 3, 4, 5, 1, 4, 4, 6, 7]
test_list2 = [4, 6, 1]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Sum of each List element occurrence in another
# using nested loops
res = 0
for ele in test_list2:
    for ele1 in test_list1:
        if ele1 == ele:
            res = res + 1

# printing result 
print ("The occurrence count : " + str(res))
```

**Output :**

```py
The original list 1 is : [1, 3, 4, 5, 1, 4, 4, 6, 7]
The original list 2 is : [4, 6, 1]
The occurrence count : 6

```