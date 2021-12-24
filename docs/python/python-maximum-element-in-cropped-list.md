# Python–裁剪列表中的最大元素

> 原文:[https://www . geesforgeks . org/python-裁剪列表中的最大元素/](https://www.geeksforgeeks.org/python-maximum-element-in-cropped-list/)

有时候，在使用 Python 时，我们可能会遇到一个问题，需要获得最大的列表。但有时，我们需要在自定义索引之间得到这个。这可以是任何领域的需要，无论是正常的编程或网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `max()`**
这是我们执行这个任务的蛮力方法。在这种情况下，我们只需在新列表中添加指定范围内的元素。然后 max()用于计算最大值。

```py
# Python3 code to demonstrate 
# Maximum element in Cropped List
# using loop + max()

# initializing list 
test_list = [2, 3, 5, 7, 9, 10, 8, 6]

# printing original list
print ("The original list is : " + str(test_list))

i, j = 2, 5

# Maximum element in Cropped List
# using loop + max()
res = []
for idx, ele in enumerate(test_list):
    if idx >= i and idx < j:
        res.append(ele)
res = max(res)

# printing result 
print ("The maximum element in range is : " + str(res))
```

**Output :**

```py
The original list is : [2, 3, 5, 7, 9, 10, 8, 6]
The maximum element in range is : 9

```