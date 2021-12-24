# Python 程序查找列表中的第二大数字

> 原文:[https://www . geesforgeks . org/python-program-to-find-第二大列表中的数字/](https://www.geeksforgeeks.org/python-program-to-find-second-largest-number-in-a-list/)

给定一个数字列表，任务是编写一个 Python 程序来查找给定列表中的第二大数字。
**例:**

```py
Input: list1 = [10, 20, 4]
Output: 10

Input: list2 = [70, 11, 20, 4, 100]
Output: 70
```

**方法 1:** 排序是一种比较容易但不太理想的方法。下面给出了一个 O(n)算法来做同样的事情。

## 蟒蛇 3

```py
# Python program to find second largest
# number in a list

# list of numbers - length of
# list should be at least 2
list1 = [10, 20, 4, 45, 99]

mx=max(list1[0],list1[1])
secondmax=min(list1[0],list1[1])
n =len(list1)
for i in range(2,n):
    if list1[i]>mx:
        secondmax=mx
        mx=list1[i]
    elif list1[i]>secondmax and \
        mx != list1[i]:
        secondmax=list1[i]

print("Second highest number is : ",\
      str(secondmax))
```

**Output**

```py
Second highest number is :  45
```