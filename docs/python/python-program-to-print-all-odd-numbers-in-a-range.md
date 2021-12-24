# 打印一个范围内所有奇数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序打印范围内所有奇数/](https://www.geeksforgeeks.org/python-program-to-print-all-odd-numbers-in-a-range/)

给定起点和终点，编写一个 Python 程序来打印给定范围内的所有奇数。

**示例:**

```py
Input: start = 4, end = 15
Output: 5, 7, 9, 11, 13, 15

Input: start = 3, end = 11
Output: 3, 5, 7, 9, 11
```

**示例#1:** 使用 for 循环打印给定列表中的所有奇数

定义范围的开始和结束限制。使用 for 循环从开始迭代到列表中的范围，并检查 num % 2！= 0.如果条件满足，则只打印数字。

```py
# Python program to print odd Numbers in given range

start, end = 4, 19

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num % 2 != 0:
        print(num, end = " ")
```

**输出:**

```py
5 7 9 11 13 15 17 19 
```

**示例#2:** 从用户输入中获取范围限制

```py
# Python program to print Even Numbers in given range

start = int(input("Enter the start of range: "))
end = int(input("Enter the end of range: "))

# iterating each number in list
for num in range(start, end + 1):

    # checking condition
    if num % 2 != 0:
        print(num, end = " ")
```

**输出:**

```py
Enter the start of range: 3
Enter the end of range: 11
3 5 7 9 11 
```

**示例#3:** 从用户输入中获取范围限制

```py
# Python program to print Even Numbers in given range

start = int(input("Enter the start of range: "))
end = int(input("Enter the end of range: "))

#create a list that contains only Even numbers in given range
even_list = range(start, end + 1)[start%2::2]

for num in even_list:
    print(num, end = " ")
```

**输出:**

```py
Enter the start of range: 3
Enter the end of range: 11
3 5 7 9 11 
```