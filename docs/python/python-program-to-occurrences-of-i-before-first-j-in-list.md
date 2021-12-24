# Python 编程到列表中第一个 j 之前出现 I 的情况

> 原文:[https://www . geesforgeks . org/python-程序到事件列表中第一个 j 之前的 I/](https://www.geeksforgeeks.org/python-program-to-occurrences-of-i-before-first-j-in-list/)

给定一个列表，任务是编写一个 Python 程序来计算第 i <sup>个</sup>元素在第 j <sup>个</sup>元素出现之前的出现次数。

**示例:**

> **输入** : test_list = [4，5，6，4，1，4，8，5，4，3，4，9]，I，j = 4，8
> **输出** : 3
> **解释** : 4 在 8 发生前发生 3 次。
> 
> **输入** : test_list = [4，5，6，4，1，4，8，5，4，3，4，9]，I，j = 5，8
> **输出** : 1
> **解释** : 5 发生在 8 发生前 1 次。

**方法#1:使用** [**循环。**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，只要遇到 I，我们就递增计数器，当任何 j 出现时，我们就停止，即从循环中断开。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Occurrences of i before first j
# Using loop

# initializing Matrix
test_list = [4, 5, 6, 4, 1, 4, 8, 5, 4, 3, 4, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j 
i, j = 4, 8

res = 0
for ele in test_list:

    # breaking on 1st j
    if ele == j:
        break

    # counting i till 1st j
    if ele == i:
        res += 1

# printing result
print("Number of i's till 1st j : " + str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 4, 1, 4, 8, 5, 4, 3, 4, 9]
Number of i's till 1st j : 3
```

**方法 2:使用** [**指数()**](https://www.geeksforgeeks.org/python-list-index/) **+** [**切片**](https://www.geeksforgeeks.org/python-list-slicing/) **+** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

在这种情况下，我们执行获取 j 的索引的任务，然后切片列表直到那里，count()用于获取切片列表中 I 的计数，以获得所需的结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Occurrences of i before first j
# Using index() + slicing + count()

# initializing Matrix
test_list = [4, 5, 6, 4, 1, 4, 8, 5, 4, 3, 4, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j 
i, j = 4, 8

# getting index
jidx = test_list.index(j)

# slicing list 
temp = test_list[:jidx]

# getting count 
res = temp.count(i)

# printing result
print("Number of i's till 1st j : " + str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 4, 1, 4, 8, 5, 4, 3, 4, 9]
Number of i's till 1st j : 3
```