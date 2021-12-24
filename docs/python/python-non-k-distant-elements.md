# Python–非 K 距离元素

> 原文:[https://www . geesforgeks . org/python-non-k-distant-elements/](https://www.geeksforgeeks.org/python-non-k-distant-elements/)

给定一个列表，任务是编写一个 Python 程序来提取所有元素，使得没有一个元素彼此相距 K。

**示例:**

> **输入**:test _ list =【8，10，16，20，3，1，7】，K = 2
> **输出**:【16，20，7】
> **解释** : 16 + 2 = 18，16–2 = 14，两者都不在列表中，因此被过滤。
> 
> **输入**:test _ list =【8，10，16，20】，K = 2
> **输出**:【16，20，7】
> **解释** : 16 + 2 = 18，16–2 = 14，两者都不在列表中，因此被过滤。

**方法#1:使用循环**

在这种情况下，我们对所有元素进行迭代，并使用 In 运算符检查每个元素是否有与它相距 K 距离的元素，如果找到，则它不包含在列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Non K distant elements
# Using loop

# initializing list
test_list = [8, 10, 16, 20, 3, 1, 7]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

res = []
for ele in test_list:

    # check for K distant
    if ele + K not in test_list and ele - K not in test_list:
        res.append(ele)

# printing result
print("The filtered List : " + str(res))
```

**Output**

```
The original list is : [8, 10, 16, 20, 3, 1, 7]
The filtered List : [16, 20, 7]
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们使用列表理解使用 1 线性执行过滤和迭代任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Non K distant elements
# Using list comprehension

# initializing list
test_list = [8, 10, 16, 20, 3, 1, 7]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# using list comprehension to get all elements of non K distance
res = [ele for ele in test_list if ele +
       K not in test_list and ele - K not in test_list]

# printing result
print("The filtered List : " + str(res))
```

**Output**

```
The original list is : [8, 10, 16, 20, 3, 1, 7]
The filtered List : [16, 20, 7]
```