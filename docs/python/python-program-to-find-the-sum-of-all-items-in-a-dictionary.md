# Python 程序在字典中查找所有项目的总和

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-sum-in-a-dictionary/](https://www.geeksforgeeks.org/python-program-to-find-the-sum-of-all-items-in-a-dictionary/)

给定一个 Python 中的字典，编写一个 Python 程序来查找字典中所有条目的总和。
**例:**

```
Input : {'a': 100, 'b':200, 'c':300}
Output : 600

Input : {'x': 25, 'y':18, 'z':45}
Output : 88
```

*   **方法#1 :** 使用内置的 [sum()](https://www.geeksforgeeks.org/sum-function-python/) 函数
    使用 sum 函数查找字典值的和。

## 蟒蛇 3

```
# Python3 Program to find sum of
# all items in a Dictionary

# Function to print sum
def returnSum(myDict):

    list = []
    for i in myDict:
        list.append(myDict[i])
    final = sum(list)

    return final

# Driver Function
dict = {'a': 100, 'b':200, 'c':300}
print("Sum :", returnSum(dict))
```

*   **输出:**

```
Sum : 600
```

*   **方法#2 :** 使用 For 循环使用[值()](https://www.geeksforgeeks.org/python-dictionary-values/)函数
    迭代使用 values()函数遍历字典中的每个值，并不断将其添加到总和中。

## 蟒蛇 3

```
# Python3 Program to find sum of
# all items in a Dictionary

# Function to print sum
def returnSum(dict):

     sum = 0
     for i in dict.values():
           sum = sum + i

     return sum

# Driver Function
dict = {'a': 100, 'b':200, 'c':300}
print("Sum :", returnSum(dict))
```

*   **输出:**

```
Sum : 600
```

*   **方法#3 :** 使用 [For 循环迭代字典中的项目](https://www.geeksforgeeks.org/looping-techniques-python/)
    迭代字典中的每个项目，并简单地保持将值添加到和变量中。

## 蟒蛇 3

```
# Python3 Program to find sum of
# all items in a Dictionary

# Function to print sum
def returnSum(dict):

     sum = 0
     for i in myDict:
           sum = sum + dict[i]

     return sum

# Driver Function
dict = {'a': 100, 'b':200, 'c':300}
print("Sum :", returnSum(dict))
```

*   **输出:**

```
Sum : 600
```