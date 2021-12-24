# Python |元组范围中的切片字符串

> 原文:[https://www . geesforgeks . org/python-slice-string-from-tuple-ranges/](https://www.geeksforgeeks.org/python-slice-string-from-tuple-ranges/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要根据指定的子串范围来执行从字符串中的移除。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+列表切片**
这是执行这个任务的蛮力任务。在本文中，我们通过使用列表切片仔细省略切片范围来重新构建字符串。元组的迭代是通过循环完成的。

```
# Python3 code to demonstrate working of
# Slice String from Tuple ranges
# using loop + list slicing

# initialize list and string 
test_list = [(2, 4), (5, 9), (13, 17), (24, 27)]

test_str = "geeksforgeeks is best for geeks and programming"

# printing original list and string
print("The original list : " + str(test_list))
print("The original string : " + str(test_str))

# Slice String from Tuple ranges
# using loop + list slicing
for front, rear in reversed(test_list):
    test_str = test_str[ : front] + test_str[rear + 1:]

# printing result
print("The String after slicing is : " + str(test_str))
```

**Output :**

```
The original list : [(2, 4), (5, 9), (13, 17), (24, 27)]
The original string : geeksforgeeks is best for geeks and programming
The String after slicing is : geeksest foeks and programming

```