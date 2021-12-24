# Python 程序打印列表中的负数

> 原文:[https://www . geesforgeks . org/python-程序-打印-列表中的负数/](https://www.geeksforgeeks.org/python-program-to-print-negative-numbers-in-a-list/)

给定一个数字列表，编写一个 Python 程序来打印给定列表中的所有负数。

**示例:**

```
Input: list1 = [12, -7, 5, 64, -14]
Output: -7, -14

Input: list2 = [12, 14, -95, 3]
Output: -95
```

**示例#1:** 使用 for 循环打印给定列表中的所有负数

使用 for 循环迭代列表中的每个元素，并检查数字是否小于 0。如果条件满足，则只打印数字。

```
# Python program to print negative Numbers in a List

# list of numbers
list1 = [11, -21, 0, 45, 66, -93]

# iterating each number in list
for num in list1:

    # checking condition
    if num < 0:
       print(num, end = " ")
```

**输出:**

```
-21 -93 
```

**示例#2:** 使用 while 循环

```
# Python program to print negative Numbers in a List

# list of numbers
list1 = [-10, 21, -4, -45, -66, 93]
num = 0

# using while loop     
while(num < len(list1)):

    # checking condition
    if list1[num] < 0:
        print(list1[num], end = " ")

    # increment num 
    num += 1

```

**输出:**

```
-10 -4 -45 -66 
```

**例 3:** 使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

```
# Python program to print negative Numbers in a List

# list of numbers
list1 = [-10, -21, -4, 45, -66, 93]

# using list comprehension
neg_nos = [num for num in list1 if num < 0]

print("Negative numbers in the list: ", *neg_nos)
```

**输出:**

```
Negative numbers in the list:  -10 -21 -4 -66
```

**示例#4:** 使用[λ表达式](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

```
# Python program to print negative Numbers in a List

# list of numbers 
list1 = [-10, 21, 4, -45, -66, 93, -11] 

# we can also print negative no's using lambda exp. 
neg_nos = list(filter(lambda x: (x < 0), list1))

print("Negative numbers in the list: ", *neg_nos) 
```

**输出:**

```
Negative numbers in the list:  -10 -45 -66 -11
```