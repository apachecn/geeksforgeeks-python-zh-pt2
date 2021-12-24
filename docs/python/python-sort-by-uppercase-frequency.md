# Python–按大写频率排序

> 原文:[https://www . geesforgeks . org/python-按大写字母排序-频率/](https://www.geeksforgeeks.org/python-sort-by-uppercase-frequency/)

给定字符串列表，按大写字符的频率进行排序。

> **输入**:test _ list =[“Gfg”、“is”、“FoR”、“GEKES”]
> **输出**:[‘is’、‘Gfg’、‘FOr’、‘GEKES’]
> **解释**:字符串中分别为 0、1、2、5 个大写字母。
> 
> **输入**:test _ list =【“is”、“GEEKS”】
> **输出**:【“is”、“GEEKS”】
> **解释**:字符串中分别为 0、5 个大写字母。

**方法#1:使用 sort() + isupper()**

在本例中，我们使用 *isupper()* 和 *sort()* 执行检查大写字母的任务，以执行排序任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort by Uppercase Frequency
# Using isupper() + sort()

# helper function
def upper_sort(sub):

    # len() to get total uppercase characters
    return len([ele for ele in sub if ele.isupper()])

# initializing list
test_list = ["Gfg", "is", "BEST", "FoR", "GEEKS"]

# printing original list
print("The original list is: " + str(test_list))

# using external function to perform sorting
test_list.sort(key=upper_sort)

# printing result
print("Elements after uppercase sorting: " + str(test_list))
```

**输出:**

```py
The original list is: ['Gfg', 'is', 'BEST', 'FoR', 'GEEKS']
Elements after uppercase sorting: ['is', 'Gfg', 'FoR', 'BEST', 'GEEKS']
```

**方法 2:使用 sorted() + lambda 函数**

在这种情况下，我们使用 *sorted()* 执行排序任务，使用 *lambda* 函数而不是外部的 *sort()* 函数来执行排序任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort by Uppercase Frequency
# Using sorted() + lambda function

# initializing list
test_list = ["Gfg", "is", "BEST", "FoR", "GEEKS"]

# printing original list
print("The original list is: " + str(test_list))

# sorted() + lambda function used to solve problem
res = sorted(test_list, key=lambda sub: len(
    [ele for ele in sub if ele.isupper()]))

# printing result
print("Elements after uppercase sorting: " + str(res))
```

**输出:**

```py
The original list is: ['Gfg', 'is', 'BEST', 'FoR', 'GEEKS']
Elements after uppercase sorting: ['is', 'Gfg', 'FoR', 'BEST', 'GEEKS']
```