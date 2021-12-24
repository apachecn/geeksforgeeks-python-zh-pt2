# Python |三重列表区别

> 原文:[https://www . geesforgeks . org/python-三重列表-差异/](https://www.geeksforgeeks.org/python-triple-list-difference/)

2 个列表之间的差异之前已经处理过了，但是有时，我们可以有两个以上的列表，我们需要找到一个列表与其他列表的相互差异。这类问题在许多领域都有应用。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`map() + set()` +列表理解**

以上 3 个功能的组合可用于执行这一特定任务。可以使用 map 函数将列表转换为 set 函数设置的列表，并且可以使用列表理解来获得每个列表的新的互差列表。

```
# Python3 code to demonstrate
# triple list difference 
# using map() + set() + list comprehension

# initializing lists 
test_list1 = [1, 5, 6, 4, 7]
test_list2 = [8, 4, 3]
test_list3 = [9, 10, 3, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))
print("The original list 3 : " + str(test_list3))

# using map() + set() + list comprehension
# triple list difference 
temp1, temp2, temp3 = map(set, (test_list1, test_list2, test_list3))
res1 = [ele for ele in test_list1 if ele not in temp2 and ele not in temp3]
res2 = [ele for ele in test_list2 if ele not in temp1 and ele not in temp3]
res3 = [ele for ele in test_list3 if ele not in temp2 and ele not in temp1]

# print result
print("The mutual difference list are : "
      + str(res1) + " " + str(res2) + " " + str(res3))
```

**Output :**

```
The original list 1 : [1, 5, 6, 4, 7]
The original list 2 : [8, 4, 3]
The original list 3 : [9, 10, 3, 5]
The mutual difference list are : [1, 6, 7] [8] [9, 10]

```

**方法 2:使用 `map() + set() + "-"`运算符**

如果不想使用列表理解，这个问题也可以通过减运算符来解决。减运算符可以执行布尔匹配差来计算有效的集合差。

```
# Python3 code to demonstrate
# triple list difference 
# using map() + set() + "-" operator

# initializing lists 
test_list1 = [1, 5, 6, 4, 7]
test_list2 = [8, 4, 3]
test_list3 = [9, 10, 3, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))
print("The original list 3 : " + str(test_list3))

# using map() + set() + "-" operator
# triple list difference 
temp1, temp2, temp3 = map(set, (test_list1, test_list2, test_list3))
res1 = temp1 - temp2 - temp3
res2 = temp2 - temp3 - temp1
res3 = temp3 - temp1 - temp2
res1, res2, res3 = map(list, (res1, res2, res3))

# print result
print("The mutual difference list are : "
      + str(res1) + " " + str(res2) + " " + str(res3))
```

**Output :**

```
The original list 1 : [1, 5, 6, 4, 7]
The original list 2 : [8, 4, 3]
The original list 3 : [9, 10, 3, 5]
The mutual difference list are : [1, 6, 7] [8] [9, 10]

```