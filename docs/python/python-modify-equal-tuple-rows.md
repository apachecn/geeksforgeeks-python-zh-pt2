# Python–修改相等元组行

> 原文:[https://www . geesforgeks . org/python-modify-equal-tuple-rows/](https://www.geeksforgeeks.org/python-modify-equal-tuple-rows/)

有时，在使用 Python Records 时，我们可能会遇到一个问题，即我们需要在记录相等的情况下执行元素记录的修改。这在涉及数据的域中可能会有问题。让我们讨论执行这项任务的某些方法。

> **输入**:
> test _ list =[(12，5)]，[(13，2)]，[(6，7)]
> test _ row =[(13，2)]
> **输出** : [[(12，5)]，[(13，8)]，[(6，7)]
> 
> **输入** :
> 测试 _ 列表=[(12，5)，(7，6)]
> 测试 _ 行= [(13，2)]
> T5】输出 : [[(12，5)，(7，6)]

**方法#1:使用 loop + `enumerate()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们应用蛮力来执行检查相等性和执行所需修改的任务。

```py
# Python3 code to demonstrate working of 
# Modify Equal Tuple Rows
# Using loop + enumerate()

# initializing list
test_list = [[(12, 5), (13, 6)], [(12, 2), (13, 2)]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check row 
test_row = [(12, 2), (13, 2)]

# Modify Equal Tuple Rows
# Using loop + enumerate()
# multiple y coordinate by 4
for idx, val in enumerate(test_list):
    if val == test_row:
        temp = []
        for sub in val:
            ele = (sub[0], sub[1] * 4)
            temp.append(ele)
        test_list[idx] = temp

# printing result 
print("List after modification : " + str(test_list)) 
```

**Output :**

```py
The original list is : [[(12, 5), (13, 6)], [(12, 2), (13, 2)]]
List after modification : [[(12, 5), (13, 6)], [(12, 8), (13, 8)]]

```

**方法 2:使用列表理解**
这是另一种可以执行该任务的方式。在这种情况下，我们使用列表理解以类似于上述方法的单行方式执行任务。

```py
# Python3 code to demonstrate working of 
# Modify Equal Tuple Rows
# Using list comprehension

# initializing list
test_list = [[(12, 5), (13, 6)], [(12, 2), (13, 2)]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check row 
test_row = [(12, 2), (13, 2)]

# Modify Equal Tuple Rows
# Using list comprehension
# multiple y coordinate by 4
res = [[(sub[0], sub[1] * 4) for sub in ele] if ele == test_row else ele for ele in test_list]

# printing result 
print("List after modification : " + str(res)) 
```

**Output :**

```py
The original list is : [[(12, 5), (13, 6)], [(12, 2), (13, 2)]]
List after modification : [[(12, 5), (13, 6)], [(12, 8), (13, 8)]]

```