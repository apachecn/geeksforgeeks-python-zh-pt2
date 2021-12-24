# Python 程序查找列表中最大的数字

> 原文:[https://www . geesforgeks . org/python-程序查找列表中最大数量/](https://www.geeksforgeeks.org/python-program-to-find-largest-number-in-a-list/)

给定一个数字列表，任务是编写一个 Python 程序来查找给定列表中最大的数字。

示例:

```py
Input : list1 = [10, 20, 4]
Output : 20

Input : list2 = [20, 10, 20, 4, 100]
Output : 100
```

方法 1:对列表进行升序排序，并打印列表中的最后一个元素。

```py
# Python program to find largest
# number in a list

# list of numbers
list1 = [10, 20, 4, 45, 99]

# sorting the list
list1.sort()

# printing the last element
print("Largest element is:", list1[-1])
```

输出:

```py
Largest element is: 99
```

方法 2:使用 max()方法

```py
# Python program to find largest
# number in a list

# list of numbers
list1 = [10, 20, 4, 45, 99]

# printing the maximum element
print("Largest element is:", max(list1))
```

输出:

```py
Largest element is: 99
```

方法 3:根据用户提供的输入找到最大列表元素

```py
# Python program to find largest
# number in a list

# creating empty list
list1 = []

# asking number of elements to put in list
num = int(input("Enter number of elements in list: "))

# iterating till num to append elements in list
for i in range(1, num + 1):
    ele = int(input("Enter elements: "))
    list1.append(ele)

# print maximum element
print("Largest element is:", max(list1))
```

输出:

```py
Enter number of elements in list: 4
Enter elements: 12
Enter elements: 19
Enter elements: 1
Enter elements: 99
Largest element is: 99
```

方法 4:不使用 python 中的内置函数:

```py
# Python program to find largest
# number in a list

def myMax(list1):

    # Assume first number in list is largest
    # initially and assign it to variable "max"
    max = list1[0]

    # Now traverse through the list and compare 
    # each number with "max" value. Whichever is 
    # largest assign that value to "max'.
    for x in list1:
        if x > max :
             max = x

    # after complete traversing the list 
    # return the "max" value
    return max

# Driver code
list1 = [10, 20, 4, 45, 99]
print("Largest element is:", myMax(list1))
```

输出:

```py
Largest element is: 99
```