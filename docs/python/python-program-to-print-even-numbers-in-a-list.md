# Python 程序打印列表中的偶数

> 原文:[https://www . geesforgeks . org/python-程序打印列表中的偶数/](https://www.geeksforgeeks.org/python-program-to-print-even-numbers-in-a-list/)

给定一个数字列表，编写一个 Python 程序来打印给定列表中的所有偶数。

**示例:**

```py
Input: list1 = [2, 7, 5, 64, 14]
Output: [2, 64, 14]

Input: list2 = [12, 14, 95, 3]
Output: [12, 14]
```

### **方法 1:** [**用于循环**](https://www.geeksforgeeks.org/loops-in-python/)

使用 for 循环迭代列表中的每个元素，并检查 num % 2 == 0。如果条件满足，则只打印数字。

## 蟒蛇 3

```py
# Python program to print Even Numbers in a List

# list of numbers
list1 = [10, 21, 4, 45, 66, 93]

# iterating each number in list
for num in list1:

    # checking condition
    if num % 2 == 0:
        print(num, end=" ")
```

**输出:**

```py
10, 4, 66
```

### **方法二:** [**使用 while 循环**](https://www.geeksforgeeks.org/loops-in-python/)

## 蟒蛇 3

```py
# Python program to print Even Numbers in a List

# list of numbers
list1 = [10, 24, 4, 45, 66, 93]
num = 0

# using while loop
while(num < len(list1)):

    # checking condition
    if list1[num] % 2 == 0:
        print(list1[num], end=" ")

    # increment num
    num += 1
```

**输出:**

```py
10, 4, 66
```

### **方法三:** [**使用列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

## 蟒蛇 3

```py
# Python program to print even Numbers in a List

# list of numbers
list1 = [10, 21, 4, 45, 66, 93]

# using list comprehension
even_nos = [num for num in list1 if num % 2 == 0]

print("Even numbers in the list: ", even_nos)
```

**输出:**

```py
Even numbers in the list:  [10, 4, 66]
```

### **方法 4:** [**使用λ表达式**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

## 蟒蛇 3

```py
# Python program to print Even Numbers in a List

# list of numbers
list1 = [10, 21, 4, 45, 66, 93, 11]

# we can also print even no's using lambda exp.
even_nos = list(filter(lambda x: (x % 2 == 0), list1))

print("Even numbers in the list: ", even_nos)
```

**输出:**

```py
Even numbers in the list:  [10, 4, 66]
```