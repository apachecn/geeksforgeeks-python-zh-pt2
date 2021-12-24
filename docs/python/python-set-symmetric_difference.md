# Python 集对称 _ 差异()

> 原文:[https://www . geesforgeks . org/python-set-symmetric _ difference/](https://www.geeksforgeeks.org/python-set-symmetric_difference/)

两个集合 set1 和 set2 的对称差是集合 set1 或 set2 中的元素集合，但不是两者都有。

![symmetric-difference](img/c3e23e0627d05f2602f1f7addd425713.png)
**语法:**

```
set1_name.symmetric_difference(set2_name) 
```

**参数:**
它只取单个集合作为参数。如果传递了一个列表、元组或字典，它会将其转换为集合并执行任务。

**返回值:**

```
Returns a set which is the symmetric difference between the two sets. 
```

对称差()的工作代码:

```
# Python program to demonstrate the use of 
# of symmetric_difference() method 

list1 = [1, 2, 3] 
list2 = [2, 3, 4] 
list3 = [3, 4, 5] 

# Convert list to sets
set1 = set(list1) 
set2 = set(list2) 

# Prints the symmetric difference when  
# set is passed as a parameter 
print(set1.symmetric_difference(set2)) 

# Prints the symmetric difference when list is 
# passed as a parameter by converting it to a set
print(set2.symmetric_difference(list3))
```

输出:

```
{1, 4}
{2, 5}

```