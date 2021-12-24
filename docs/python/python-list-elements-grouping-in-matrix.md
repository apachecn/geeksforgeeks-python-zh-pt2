# Python–在矩阵中列出元素分组

> 原文:[https://www . geesforgeks . org/python-list-elements-group-in-matrix/](https://www.geeksforgeeks.org/python-list-elements-grouping-in-matrix/)

给定一个矩阵，根据列表元素分组，即每个组应包含列表中的所有元素。

> **输入** : test_list = [[2，6]，[7，8]，[1，4]]，check_list = [1，2，4，6]
> **输出** : [[7，8]，[[1，2]，[4，6]]
> **解释** : 1，2，4，6 元素行分组。
> 
> **输入** : test_list = [[2，7]，[7，8]，[1，4]]，check_list = [1，2，4，6]
> **输出** : [[2，7]，[7，8]，[1，4]]
> **解释**:不可能分组。

**方法:使用循环+列表理解+尝试-除了**

在这种情况下，对于矩阵中的每一行，从列表中获取缺失的元素，在获取元素后，与每一行匹配，如果我们能找到缺失的元素，如果找到，则组成新的组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# List Elements Grouping in Matrix
# Using loop 

# initializing list
test_list = [[4, 6], [1, 2], [2, 6], [7, 8], [1, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check_list
check_list = [1, 2, 4, 6]

res = []
while test_list:

    # getting row
    sub1 = test_list.pop()

    # getting elements not in row
    sub2 = [ele for ele in check_list if ele not in sub1]
    try:

        # testing if we have list of removed elements
        test_list.remove(sub2)

        # grouping if present
        res.append([sub1, sub2])
    except ValueError:

        # ungrouped. 
        res.append(sub1)

# printing result 
print("The Grouped rows : " + str(res))
```

**Output**

```
The original list is : [[4, 6], [1, 2], [2, 6], [7, 8], [1, 4]]
The Grouped rows : [[[1, 4], [2, 6]], [7, 8], [[1, 2], [4, 6]]]

```