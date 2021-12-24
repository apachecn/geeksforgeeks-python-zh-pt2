# Python |乘法至空值

> 原文:[https://www . geesforgeks . org/python-乘法-till-null-value/](https://www.geeksforgeeks.org/python-multiplication-till-null-value/)

前缀数组在编程界相当有名。本文将讨论这个方案的一个变体。这将处理累计列表产品，直到出现假值，并再次从出现真值开始累计产品。让我们讨论一下实现这一点的特定方式。

**方法#1:使用天真的方法**
在天真的方法中，我们只需构建包含 prev 乘积的新列表。值，直到出现 False，并在遇到 True 值时重新启动过程。

```
# Python3 code to demonstrate 
# Multiplication till Null value
# using naive method 

# initializing list of lists
test_list = [1, 3, 4, False, 4, 5, False, 7, 8]

# printing original list
print ("The original list is : " + str(test_list))

# Multiplication till Null value
# using naive method
for i in range(1, len(test_list)):
    if test_list[i]: 
        test_list[i] *= test_list[i - 1]
    else:
        test_list[i] = 1

# printing result
print ("The computed modified new list : " + str(test_list))
```

**Output :**

```
The original list is : [1, 3, 4, False, 4, 5, False, 7, 8]
The computed modified new list : [1, 3, 12, 1, 4, 20, 1, 7, 56]

```