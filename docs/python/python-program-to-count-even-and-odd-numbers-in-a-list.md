# Python 程序统计列表中的偶数和奇数

> 原文:[https://www . geesforgeks . org/python-程序对列表中的偶数和奇数进行计数/](https://www.geeksforgeeks.org/python-program-to-count-even-and-odd-numbers-in-a-list/)

给定一个数字列表，编写一个 Python 程序来计算列表中的偶数和奇数。

示例:

```
Input: list1 = [2, 7, 5, 64, 14]
Output: Even = 3, odd = 2

Input: list2 = [12, 14, 95, 3]
Output: Even = 2, odd = 2
```

示例 1:使用 for 循环计算给定列表中的偶数和奇数

使用 for 循环迭代列表中的每个元素，并检查 num % 2 == 0，这是检查偶数的条件。如果条件满足，则增加偶数计数，否则增加奇数计数。

```
# Python program to count Even
# and Odd numbers in a List

# list of numbers
list1 = [10, 21, 4, 45, 66, 93, 1]

even_count, odd_count = 0, 0

# iterating each number in list
for num in list1:

    # checking condition
    if num % 2 == 0:
        even_count += 1

    else:
        odd_count += 1

print("Even numbers in the list: ", even_count)
print("Odd numbers in the list: ", odd_count)
```

**Output:**

```
Even numbers in the list:  3
Odd numbers in the list:  4

```

示例 2:使用 while 循环

```
# Python program to count Even and Odd numbers in a List

# list of numbers
list1 = [10, 21, 4, 45, 66, 93, 11]

even_count, odd_count = 0, 0
num = 0

# using while loop     
while(num < len(list1)):

    # checking condition
    if list1[num] % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

    # increment num 
    num += 1

print("Even numbers in the list: ", even_count)
print("Odd numbers in the list: ", odd_count)
```

**Output:**

```
Even numbers in the list:  3
Odd numbers in the list:  4

```

示例 3:使用 [Python Lambda 表达式](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

```
# list of numbers
list1 = [10, 21, 4, 45, 66, 93, 11]

odd_count = len(list(filter(lambda x: (x%2 != 0) , list1)))

# we can also do len(list1) - odd_count
even_count = len(list(filter(lambda x: (x%2 == 0) , list1)))

print("Even numbers in the list: ", even_count)
print("Odd numbers in the list: ", odd_count)
```

**Output:**

```
Even numbers in the list:  3
Odd numbers in the list:  4

```

示例 4:使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

```
# Python program to print odd Numbers in a List

# list of numbers
list1 = [10, 21, 4, 45, 66, 93, 11]

only_odd = [num for num in list1 if num % 2 == 1]
odd_count = len(only_odd)

print("Even numbers in the list: ", len(list1) - odd_count)
print("Odd numbers in the list: ", odd_count)
```

**Output:**

```
Even numbers in the list:  3
Odd numbers in the list:  4

```