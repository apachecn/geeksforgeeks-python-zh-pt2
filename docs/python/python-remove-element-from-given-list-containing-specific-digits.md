# Python |从包含特定数字的给定列表中移除元素

> 原文:[https://www . geesforgeks . org/python-从给定列表中移除元素-包含特定数字/](https://www.geeksforgeeks.org/python-remove-element-from-given-list-containing-specific-digits/)

给定一个列表，任务是从包含特定数字的列表中移除所有这些元素。

**示例:**

```
Input: lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]
       no_delete = ['2', '3', '4', '0']
Output: [1, 5, 6, 7, 8, 9, 11, 15, 16]
Explanation:
Numbers 2, 3, 4, 10, 12, 13, 14 contains digits 
from no_delete, therefore remove them.

Input: lst = [1, 2, 3, 4, 5, 6, 7, 8, 13, 15, 16]
       no_delete = {'6', '5', '4', '3'}
Output: [1, 2, 7, 8, 9, 10, 11, 12]
Explanation:
Numbers 3, 4, 5, 6, 13, 14, 15, 16 contains digits 
from no_delete, therefore remove them.

```

下面是一些做任务的方法。

**方法#1:使用迭代**

```
# Python code to remove all those elements 
# from list which contains certain digits

# Input List Initialisation
Input = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]

# Numbers to delete
no_delete = [1, 0]

# Output List Initialisation
Output = []

# Using iteration to remove all the elements 
for elem in Input:
    flag = 1
    temp = elem
    while elem > 0:
        rem = elem % 10
        elem = elem//10
        if rem in no_delete:
            flag = 0
    if flag == 1:
        Output.append(temp)

# Printing Output 
print("Initial list is :", Input)
print("Delete list :", no_delete)
print("List after removing elements is :", Output)
```

**Output:**

```
Initial list is : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]
Delete list : [1, 0]
List after removing elements is : [2, 3, 4, 5, 6, 7, 8, 9]

```

**方法 2:使用列表理解和任意()函数**

```
# Python code to remove all those elements from list 
# which contains certain digits

# Input List Initialisation
Input = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]

# Numbers to delete
no_delete = ['2', '3', '4', '0']

# using list comprehension and any()
Output = [a for a in Input if not 
          any(b in no_delete for b in str(a))]

# Printing Output 
print("Initial list is :", Input)
print("Delete list :", no_delete)
print("List after removing elements is :", Output)
```

**Output:**

```
Initial list is : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]
Delete list : ['2', '3', '4', '0']
List after removing elements is : [1, 5, 6, 7, 8, 9, 11, 15, 16]

```

**方法三:利用列表理解和集合()**

```
# Python code to remove all those elements from list 
# which contains certain digits

# Input List Initialisation
Input = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]

# Numbers to delete
no_delete = {'6', '5', '4', '3'}

# Using list comprehension and set
Output = [x for x in Input
         if not no_delete & set(str(x))]

# Printing Output 
print("Initial list is :", Input)
print("Delete list :", no_delete)
print("List after removing elements is :", Output)
```

**Output:**

```
Initial list is : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 13, 15, 16]
Delete list : {'3', '4', '6', '5'}
List after removing elements is : [1, 2, 7, 8, 9, 10, 11, 12]

```