# Python–包含所有列表元素的行

> 原文:[https://www . geesforgeks . org/python-row-with-all-list-elements/](https://www.geeksforgeeks.org/python-rows-with-all-list-elements/)

给定一个矩阵，获取包含所有列表元素的所有行。

> **输入** : test_list = [[7，6，3，2]，[5，6]，[2，1，8]，[6，1，2]]，sub_list = [1，2]
> **输出** : [[2，1，8]，[6，1，2]]
> **解释**:提取的列表有 1 和 2。
> 
> **输入** : test_list = [[7，6，3，2]，[5，6]，[2，1，8]，[6，1，2]]，sub_list = [2，6]
> **输出** : [[7，6，3，2]，[6，1，2]]
> **解释**:提取的列表有 2 和 6。

**方法#1:使用循环**

在这种情况下，我们对矩阵中的每一行进行迭代，并检查每个列表元素是否存在，如果存在，则返回结果行。如果任何元素不存在，该行将被标记为关闭。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Rows with all List elements
# Using loop

# initializing list
test_list = [[7, 6, 3, 2], [5, 6], [2, 1, 8], [6, 1, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing list
sub_list = [1, 2]

res = []
for row in test_list:

    flag = True

    # checking for all elements in list
    for ele in sub_list:
        if ele not in row:
            flag = False

    if flag:
        res.append(row)

# printing result
print("Rows with list elements : " + str(res))
```

**输出:**

> 原始列表为:[[7，6，3，2]，[5，6]，[2，1，8]，[6，1，2]]
> 包含列表元素的行:[[2，1，8]，[6，1，2]]

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，使用 all()测试的所有在场元素，列表理解被用作一行来执行遍历行的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Rows with all List elements
# Using all() + list comprehension

# initializing list
test_list = [[7, 6, 3, 2], [5, 6], [2, 1, 8], [6, 1, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing list  
sub_list = [1, 2]

# testing elements presence using all()
res = [row for row in test_list if all(ele in row for ele in sub_list)]

# printing result 
print("Rows with list elements : " + str(res))
```

**输出:**

> 原始列表为:[[7，6，3，2]，[5，6]，[2，1，8]，[6，1，2]]
> 包含列表元素的行:[[2，1，8]，[6，1，2]]