# Python 程序打印一个范围内的所有负数

> 原文:[https://www . geesforgeks . org/python-program-to-print-全负数范围/](https://www.geeksforgeeks.org/python-program-to-print-all-negative-numbers-in-a-range/)

给定一个范围的开始和结束，编写一个 Python 程序来打印给定范围内的所有负数。

**示例:**

```py
Input: start = -4, end = 5
Output: -4, -3, -2, -1

Input: start = -3, end = 4
Output: -3, -2, -1
```

**示例#1:** 使用 for 循环打印给定列表中的所有负数

定义范围的开始和结束限制。使用 for 循环从开始迭代到列表中的范围，并检查 num 是否小于 0。如果条件满足，则只打印数字。

```py
# Python program to print negative Numbers in given range

start, end = -4, 19

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num < 0:
        print(num, end = " ")
```

**输出:**

```py
-4, -3, -2, -1 
```

**示例#2:** 从用户输入中获取范围限制

```py
# Python program to print negative Numbers in given range

start = int(input("Enter the start of range: "))
end = int(input("Enter the end of range: "))

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num < 0:
        print(num, end = " ")
```

**输出:**

```py
Enter the start of range: -15
Enter the end of range: 5
-15 -14 -13 -12 -11 -10 -9 -8 -7 -6 -5 -4 -3 -2 -1 
```