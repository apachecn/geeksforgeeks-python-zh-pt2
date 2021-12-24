# Python |移除给定范围之外的所有子列表

> 原文:[https://www . geesforgeks . org/python-remove-all-sublist-超出给定范围/](https://www.geeksforgeeks.org/python-remove-all-sublists-outside-the-given-range/)

给定列表和范围，任务是遍历每个子列表并移除包含超出给定范围的元素的子列表。

**示例:**

```py
Input : 
left= 10, right = 17, list = [[0, 1.2, 3.4, 18.1, 10.1],
                              [10.3, 12.4, 15, 17, 16, 11],
                              [100, 10, 9.2, 11, 13, 17.1], ]

Output: [[10.3, 12.4, 15, 17, 16, 11]]

Input : 
left= 1, right = 9, list = [[11, 12, 15, 17, 3],
                            [3, 1, 4, 5.2, 9, 19],
                            [2, 4, 6, 7.2, 8.9]]

Output: [[2, 4, 6, 7.2, 8.9]]
```

**方法#1 :** 遍历每个子列表。

```py
# Python code to remove all the 
# sublist outside the given range

# Initialisation of list of list
list = [[0,1.2,3.4,18.1,10.1], 
        [10.3,12.4,15,17,16,11],
        [1000,100,10,3.2,11,13, 17.1], ]

# Defining range
left, right = 10, 17

# initialization of index
b=0

for t in list:
    a=0
    for k in t:
        if k<left or k>right:
            a=1
    if a==1:
        list.pop(b)
    b=b+1

# printing output
print(list)
```

**Output:**

```py
[[10.3, 12.4, 15, 17, 16, 11]]

```

**方法 2:** 使用列表理解

```py
# Python code to remove all the 
# sublist outside the given range

# Initialisation of list of list
list = [[11, 12, 15, 17, 3],
        [3, 1, 4, 5.2, 9, 19],
        [2, 4, 6, 7.2, 8.9]]

# Defining range
left = 1
right = 9

# Using list comprehension
Output = [i for i in list if (min(i)>=left and max(i)<=right)]

# Printing output
print (Output)
```

**Output:**

```py
[[2, 4, 6, 7.2, 8.9]]

```