# Python 程序对列表中的正数和负数进行计数

> 原文:[https://www . geesforgeks . org/python-程序到计数-列表中的正数和负数/](https://www.geeksforgeeks.org/python-program-to-count-positive-and-negative-numbers-in-a-list/)

给定一个数字列表，编写一个 Python 程序来计算列表中的正数和负数。

**示例:**

```py
Input: list1 = [2, -7, 5, -64, -14]
Output: pos = 2, neg = 3

Input: list2 = [-12, 14, 95, 3]
Output: pos = 3, neg = 1
```

**示例#1:** 使用 for 循环从给定列表中计数正数和负数

使用 for 循环迭代列表中的每个元素，并检查 num 是否> = 0，这是检查正数的条件。如果条件满足，则增加 pos_count，否则增加 neg_count。

```py
# Python program to count positive and negative numbers in a List

# list of numbers
list1 = [10, -21, 4, -45, 66, -93, 1]

pos_count, neg_count = 0, 0

# iterating each number in list
for num in list1:

    # checking condition
    if num >= 0:
        pos_count += 1

    else:
        neg_count += 1

print("Positive numbers in the list: ", pos_count)
print("Negative numbers in the list: ", neg_count)
```

**输出:**

```py
Positive numbers in the list:  4
Negative numbers in the list:  3

```

**示例#2:** 使用 while 循环

```py
# Python program to count positive and negative numbers in a List

# list of numbers
list1 = [-10, -21, -4, -45, -66, 93, 11]

pos_count, neg_count = 0, 0
num = 0

# using while loop     
while(num < len(list1)):

    # checking condition
    if list1[num] >= 0:
        pos_count += 1
    else:
        neg_count += 1

    # increment num 
    num += 1

print("Positive numbers in the list: ", pos_count)
print("Negative numbers in the list: ", neg_count)
```

**输出:**

```py
Positive numbers in the list:  2
Negative numbers in the list:  5

```

**示例#3 :** 使用 [Python Lambda 表达式](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

```py
# Python program to count positive
# and negative numbers in a List

# list of numbers
list1 = [10, -21, -4, 45, 66, 93, -11]

neg_count = len(list(filter(lambda x: (x < 0), list1)))

# we can also do len(list1) - neg_count
pos_count = len(list(filter(lambda x: (x >= 0), list1)))

print("Positive numbers in the list: ", pos_count)
print("Negative numbers in the list: ", neg_count)
```

**输出:**

```py
Positive numbers in the list:  4
Negative numbers in the list:  3

```

**示例#4 :** 使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

```py
# Python program to count positive
# and negative numbers in a List

# list of numbers
list1 = [-10, -21, -4, -45, -66, -93, 11]

only_pos = [num for num in list1 if num >= 1]
pos_count = len(only_pos)

print("Positive numbers in the list: ", pos_count)
print("Negative numbers in the list: ", len(list1) - pos_count)
```

**输出:**

```py
Positive numbers in the list:  1
Negative numbers in the list:  6

```