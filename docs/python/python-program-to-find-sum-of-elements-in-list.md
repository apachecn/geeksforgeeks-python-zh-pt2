# Python 程序求列表中元素的和

> 原文:[https://www . geesforgeks . org/python-program-to-find-sum-in-list 元素/](https://www.geeksforgeeks.org/python-program-to-find-sum-of-elements-in-list/)

给定一个数字列表，编写一个 Python 程序来查找列表中所有元素的总和。
**例:**

```py
Input: [12, 15, 3, 10]
Output: 40

Input: [17, 5, 3, 5]
Output: 30
```

**示例#1:**

## 蟒蛇 3

```py
# Python program to find sum of elements in list
total = 0

# creating a list
list1 = [11, 5, 17, 18, 23]

# Iterate each element in list
# and add them in variable total
for ele in range(0, len(list1)):
    total = total + list1[ele]

# printing total value
print("Sum of all elements in given list: ", total)
```

**输出:**

```py
Sum of all elements in given list:  74
```

**示例#2 :** 使用 while()循环

## 蟒蛇 3

```py
# Python program to find sum of elements in list
total = 0
ele = 0

# creating a list
list1 = [11, 5, 17, 18, 23]

# Iterate each element in list
# and add them in variable total
while(ele < len(list1)):
    total = total + list1[ele]
    ele += 1

# printing total value
print("Sum of all elements in given list: ", total)
```

**输出:**

```py
Sum of all elements in given list:  74
```

**例 3:** 递归方式

## 蟒蛇 3

```py
# Python program to find sum of all
# elements in list using recursion

# creating a list
list1 = [11, 5, 17, 18, 23]

# creating sum_list function
def sumOfList(list, size):
   if (size == 0):
     return 0
   else:
     return list[size - 1] + sumOfList(list, size - 1)

# Driver code    
total = sumOfList(list1, len(list1))

print("Sum of all elements in given list: ", total)
```

**输出:**

```py
Sum of all elements in given list:  74
```

**例#4:** 使用 [sum()方法](https://www.geeksforgeeks.org/sum-function-python/)T5】

## 蟒蛇 3

```py
# Python program to find sum of elements in list

# creating a list
list1 = [11, 5, 17, 18, 23]

# using sum() function
total = sum(list1)

# printing total value
print("Sum of all elements in given list: ", total)
```

**输出:**

```py
Sum of all elements in given list:  74
```