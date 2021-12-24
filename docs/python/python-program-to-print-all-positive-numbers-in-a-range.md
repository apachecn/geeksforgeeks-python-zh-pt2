# Python 程序打印一个范围内的所有正数

> 原文:[https://www . geesforgeks . org/python-program-to-print-all-正数范围/](https://www.geeksforgeeks.org/python-program-to-print-all-positive-numbers-in-a-range/)

给定一个范围的开始和结束，编写一个 Python 程序来打印给定范围内的所有正数。

**示例:**

```py
Input: start = -4, end = 5
Output: 0, 1, 2, 3, 4, 5 

Input: start = -3, end = 4
Output: 0, 1, 2, 3, 4
```

**示例#1:** 使用 for 循环打印给定列表中的所有正数

定义范围的开始和结束限制。使用 for 循环从开始迭代到列表中的范围，并检查 num 是否大于或等于 0。如果条件满足，则只打印数字。

```py
# Python program to print positive Numbers in given range

start, end = -4, 19

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num >= 0:
        print(num, end = " ")
```

**输出:**

```py
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 
```

**示例#2:** 从用户输入中获取范围限制

```py
# Python program to print positive Numbers in given range

start = int(input("Enter the start of range: "))
end = int(input("Enter the end of range: "))

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num >= 0:
        print(num, end = " ")
```

**输出:**

```py
Enter the start of range: -215
Enter the end of range: 5
0 1 2 3 4 5 
```