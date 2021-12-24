# Python |列表相似度百分比

> 原文:[https://www . geesforgeks . org/python-列表相似度百分比/](https://www.geeksforgeeks.org/python-percentage-similarity-of-lists/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要找到一个列表与其他列表的相似程度。这两个列表的相似商是我们在许多场景中可能需要的。让我们讨论一下执行这项任务的方法。

**方法:使用`"|" operator + "&" operator + set()`**
形式上应用于计算列表间相似度的方法是找出不同的元素和共同的元素，并计算其商。然后将结果乘以 100，得到百分比。

```py
# Python3 code to demonstrate working of
# Percentage similarity of lists
# using "|" operator + "&" operator + set()

# initialize lists
test_list1 = [1, 4, 6, 8, 9, 10, 7]
test_list2 = [7, 11, 12, 8, 9]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Percentage similarity of lists
# using "|" operator + "&" operator + set()
res = len(set(test_list1) & set(test_list2)) / float(len(set(test_list1) | set(test_list2))) * 100

# printing result
print("Percentage similarity among lists is : " + str(res))
```

**Output :**

```py
The original list 1 is : [1, 4, 6, 8, 9, 10, 7]
The original list 2 is : [7, 11, 12, 8, 9]
Percentage similarity among lists is : 33.33333333333333

```