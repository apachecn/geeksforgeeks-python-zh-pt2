# Python |打印两个列表的所有公共元素

> 原文:[https://www . geesforgeks . org/python-print-common-elements-two-list/](https://www.geeksforgeeks.org/python-print-common-elements-two-lists/)

给定两个列表，打印两个列表的所有公共元素。

**示例:**

```
Input : list1 = [1, 2, 3, 4, 5] 
        list2 = [5, 6, 7, 8, 9]
Output : {5}
Explanation: The common elements of 
both the lists are 3 and 4 

Input : list1 = [1, 2, 3, 4, 5] 
        list2 = [6, 7, 8, 9]
Output : No common elements 
Explanation: They do not have any 
elements in common in between them
```

### **方法 1:使用 Set 的&属性**

将列表转换为集合，然后打印**集合 1 &集合 2** 。set1 & set2 返回公共元素集，其中 set1 为 list1，set2 为 list2。
*下图是上述方法的 Python3 实现:*

## 蟒蛇 3

```
# Python program to find the common elements
# in two lists
def common_member(a, b):
    a_set = set(a)
    b_set = set(b)

    if (a_set & b_set):
        print(a_set & b_set)
    else:
        print("No common elements")

a = [1, 2, 3, 4, 5]
b = [5, 6, 7, 8, 9]
common_member(a, b)

a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9]
common_member(a, b)
```

**输出:**

```
{5}
No common elements
```

### **方法 2:使用集合的交集属性**

通过转换将列表转换为集合。使用[交集](https://www.geeksforgeeks.org/intersection-function-python/)功能检查两个集合是否有任何共同的元素。如果它们有许多共同的元素，则打印两个集合的交集。
下面是上述方法的 Python3 实现:

## 蟒蛇 3

```
# Python program to find common elements in
# both sets using intersection function in
# sets

# function
def common_member(a, b):   
    a_set = set(a)
    b_set = set(b)

    # check length
    if len(a_set.intersection(b_set)) > 0:
        return(a_set.intersection(b_set)) 
    else:
        return("no common elements")

a = [1, 2, 3, 4, 5]
b = [5, 6, 7, 8, 9]
print(common_member(a, b))

a =[1, 2, 3, 4, 5]
b =[6, 7, 8, 9]
print(common_member(a, b))
```

**输出:**

```
{5}
No common elements
```