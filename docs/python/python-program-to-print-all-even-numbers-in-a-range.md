# 打印一个范围内所有偶数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-打印-范围内所有偶数/](https://www.geeksforgeeks.org/python-program-to-print-all-even-numbers-in-a-range/)

给定起点和终点，编写一个 Python 程序来打印给定范围内的所有偶数。

**示例:**

```
Input: start = 4, end = 15
Output: 4, 6, 8, 10, 12, 14

Input: start = 8, end = 11
Output: 8, 10
```

**示例#1:** 使用 for 循环打印给定列表中的所有偶数

定义范围的开始和结束限制。使用 for 循环从头至尾迭代列表中的范围，并检查 num % 2 == 0。如果条件满足，则只打印数字。

```
# Python program to print Even Numbers in given range

start, end = 4, 19

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num % 2 == 0:
        print(num, end = " ")
```

**输出:**

```
4 6 8 10 12 14 16 18 
```

**示例#2:** 从用户输入中获取范围限制

```
# Python program to print Even Numbers in given range

start = int(input("Enter the start of range: "))
end = int(input("Enter the end of range: "))

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num % 2 == 0:
        print(num, end = " ")
```

**输出:**

```
Enter the start of range: 4
Enter the end of range: 10
4 6 8 10 
```