# Python 中列表(带字符串类型)之和

> 原文:[https://www . geesforgeks . org/python 中字符串类型列表总和/](https://www.geeksforgeeks.org/sum-of-list-with-string-types-in-python/)

在 Python 中，数据类型的行为类型不会改变。下面的例子是包含字符串形式的整数类型的列表，因此，我们必须从列表中取出所有 int 类型的数字，即使它是用字符串声明的。

示例:

```
Input : list1 = [12, 'geek', 2, '41', 'for', 10, '8', 6, 4, 'geeks', 7, '10']
Output : 100

Input : list1 = [100, 'geek', 200, '400', 'for', 101, '2018', 
                               64, 74, 'geeks', 27, '7810']
Output :10794

```

我们使用 Python 中的 [type()和 Python 中的](https://www.geeksforgeeks.org/python-type-function/) [isdigit()来实现这一点。](https://www.geeksforgeeks.org/python-string-isdigit-application/)

```
# Python program to find sum of list with different
# types.

def calsum(l):

    # returning sum of list using List comprehension
    return  sum([int(i) for i in l if type(i)== int or i.isdigit()])

# Declaring list
list1 = [12, 'geek', 2, '41', 'for', 10, '8', 6, 4, 'geeks', 7, '10']
list2 = [100, 'geek', 200, '400', 'for', 101, '2018', 64, 74, 'geeks', 27, '7810']

# Result of sum of list
print (calsum(list1))
print (calsum(list2))
```