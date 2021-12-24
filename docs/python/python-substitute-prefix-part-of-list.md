# Python–替换列表的前缀部分

> 原文:[https://www . geesforgeks . org/python-replace-prefix-part-of-list/](https://www.geeksforgeeks.org/python-substitute-prefix-part-of-list/)

给定 2 个列表，将一个列表替换为其他列表的前缀元素。

> **输入** : test_list1 = [4，6，8，7]，test_list2 = [2，7，9，4，2，8]
> **输出** : [4，6，8，7，2，8]
> **解释** : 4，6，8，7 来自列表 1，其余，2，8 来自列表 2，替换列表 2 的前缀。
> **输入** : test_list1 = [4，6]，test_list2 = [2，7，9，4，2，8]
> **输出** : [4，6，9，4，2，8]
> **解释**:列表 1 中的 4，6 和 rest，列表 2 中的 9，4，2 和 8，替换列表 2 的前缀。

**方法#1:使用 len() +列表切片**

在这种情况下，我们使用 len()和列表切片，在列表 1 的大小之后添加列表 1，然后添加列表 2 的一部分。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Substitute prefix part of List
# Using len() + list slicing

# initializing lists
test_list1 = [4, 6, 8, 7]
test_list2 = [2, 7, 9, 4, 2, 8, 6, 4, 1, 10]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# size slicing after length of list 1
res = test_list1 + test_list2[len(test_list1) : ]

# printing result
print("The joined list : " + str(res))
```

**Output**

```py
The original list 1 : [4, 6, 8, 7]
The original list 2 : [2, 7, 9, 4, 2, 8, 6, 4, 1, 10]
The joined list : [4, 6, 8, 7, 2, 8, 6, 4, 1, 10]
```

**方法 2:使用*运算符**

在这种情况下，我们使用*操作符来执行打包和解包到新列表的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Substitute prefix part of List
# Using * operator

# initializing lists
test_list1 = [4, 6, 8, 7]
test_list2 = [2, 7, 9, 4, 2, 8, 6, 4, 1, 10]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# * operator reconstructs lists
res = [*test_list1, *test_list2[len(test_list1) : ]]

# printing result
print("The joined list : " + str(res))
```

**Output**

```py
The original list 1 : [4, 6, 8, 7]
The original list 2 : [2, 7, 9, 4, 2, 8, 6, 4, 1, 10]
The joined list : [4, 6, 8, 7, 2, 8, 6, 4, 1, 10]
```