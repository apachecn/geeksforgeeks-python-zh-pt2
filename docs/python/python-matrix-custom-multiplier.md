# Python–矩阵自定义乘数

> 原文:[https://www . geesforgeks . org/python-matrix-custom-multiplier/](https://www.geeksforgeeks.org/python-matrix-custom-multiplier/)

有时，在处理数据时，我们会遇到一个问题，即我们需要用不同的乘数乘以矩阵的每一行。这种应用在数据科学领域非常重要。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `zip()`**
以上功能的组合可以用来执行这个任务。在本文中，我们遍历每一行，并使用 zip()执行乘法任务。

```
# Python3 code to demonstrate 
# Matrix Custom Multiplier
# using loop + zip()

# Initializing list
test_list1 = [[1, 3], [5, 6], [8, 9]]
test_list2 = [4, 3, 6]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Matrix Custom Multiplier
# using loop + zip()
res = []
for mul, sub in zip(test_list2, test_list1):
    temp = []
    for ele in sub:
        temp.append(mul * ele)
    res.append(temp)

# printing result 
print ("Matrix after custom multiplication : " + str(res))
```

**Output :**

```
The original list 1 is : [[1, 3], [5, 6], [8, 9]]
The original list 2 is : [4, 3, 6]
Matrix after custom multiplication : [[4, 12], [15, 18], [48, 54]]

```