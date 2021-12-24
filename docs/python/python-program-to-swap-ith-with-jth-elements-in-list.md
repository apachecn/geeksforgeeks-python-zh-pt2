# Python 程序用列表

中的第 j 个元素交换第 I 个

> 原文:[https://www . geesforgeks . org/python-program-to-swap-with-jth-elements-in-list/](https://www.geeksforgeeks.org/python-program-to-swap-ith-with-jth-elements-in-list/)

给定一个列表，任务是为给定的元素列表编写一个 Python 程序，切换列表中的每个 I 和 j 元素。

**示例:**

> **输入** : test_list = [4，7，8，0，8，4，2，9，4，8，4]，I，j = 4，8
> **输出** : [8，7，4，0，4，8，2，9，8，4，8]
> **解释**:每次出现时 4 被 8 交换。
> 
> **输入** : test_list = [4，7，8，0，8，4]，I，j = 4，8
> **输出** : [8，7，4，0，4，8]
> **解释**:每次出现时 4 被换成 8。

**方法一:使用循环+条件语句**

在本文中，我们使用条件 if-else 语句执行切换任务，并使用循环执行迭代任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Toggle i,j elements in List
# Using loop + conditional statements

# initializing list
test_list = [4, 7, 8, 0, 8, 4, 2, 9, 4, 8, 4]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j 
i, j = 4, 8

for idx in range(len(test_list)):

    # perform toggling
    if int(test_list[idx]) == i:
        test_list[idx] = j
    elif int(test_list[idx]) == j:
        test_list[idx] = i

# printing result
print("The altered list : " + str(test_list))
```

**输出:**

```
The original list is : [4, 7, 8, 0, 8, 4, 2, 9, 4, 8, 4]
The altered list : [8, 7, 4, 0, 4, 8, 2, 9, 8, 4, 8]
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+外部功能**

在这种情况下，我们使用外部切换函数执行切换任务，列表理解用于遍历列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Toggle i,j elements in List
# Using list comprehension + external function

# external toggle 
def toggle(ele, i, j):

    # performing toggle
    if ele == i:
        return j
    elif ele == j:
        return i
    return ele

# initializing list
test_list = [4, 7, 8, 0, 8, 4, 2, 9, 4, 8, 4]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j 
i, j = 4, 8

# list comprehension for 1 liner
res = [toggle(ele, i, j) for ele in test_list]

# printing result
print("The altered list : " + str(res))
```

**输出:**

```
The original list is : [4, 7, 8, 0, 8, 4, 2, 9, 4, 8, 4]
The altered list : [8, 7, 4, 0, 4, 8, 2, 9, 8, 4, 8]
```