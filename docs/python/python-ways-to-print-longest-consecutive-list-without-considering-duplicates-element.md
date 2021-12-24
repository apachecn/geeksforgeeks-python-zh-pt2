# Python–打印最长连续列表而不考虑重复元素的方法

> 原文:[https://www . geesforgeks . org/python-打印方式-最长连续列表-不考虑重复-元素/](https://www.geeksforgeeks.org/python-ways-to-print-longest-consecutive-list-without-considering-duplicates-element/)

给定一个数字列表，任务是打印最长的连续(严格)列表，而不考虑重复的元素。如果答案不止一个，打印任何人。在 Django 或 flask 中处理一些 web 开发项目时，这些类型的问题非常常见。

以下是解决上述任务的一些方法。

**注意:**如果有多个答案，打印任何人

> **输入:**
> 【1、2、3、5、6、6、7、9、10、11、13、14、15、16、16、17、18、20、21】
> **输出:**
> 【13、14、15、16】
> **说明:**
> 原列表=【1、2、3、5、6、7、9、10、11

**方法 1:使用迭代**
执行此操作时想到的基本方法是打印最长连续列表的幼稚方法。

## 蟒蛇 3

```py
# Python code to print longest consecutive list.

# Input list initialization
Input = [12, 13, 14, 17, 18, 23, 24, 25, 25, 26, 27]

# Output list initialization
Output = []
temp = []
last = -1

# Iteration
for elem in Input:
    if elem - last == 1:
        temp.append(last)
    else:
        temp.append(last)
        Output.append(temp)
        temp = []
    last = elem

ans = []
most = 0

for elem in Output:
    if len(elem)> most:
        most = len(elem)
        ans = elem

# Printing output
print("Initial List is")
print(Input)
print("Longest Consecutive list is :")
print(ans)
```

**输出:**

```py
Initial List is
[12, 13, 14, 17, 18, 23, 24, 25, 25, 26, 27]
Longest Consecutive list is :
[23, 24, 25]
```

**方法二:使用 groupby 和 zip**
使用 Groupby 和 zip 是打印最长连续列表最优雅的方式。

## 蟒蛇 3

```py
# Python code to print longest consecutive list.

# Importing
from itertools import groupby

# List Initialization
Input = [1, 2, 3, 5, 6, 6, 7, 9, 10, 11, 13, 14, 15, 16, 16, 17, 18, 20, 21]

# Using zip
z = zip(Input, Input[1:])

# Using groupby
lis = [list(y) for i, y in groupby(z, key = lambda x: (x[1] - x[0]) == 1)]

# Taking max according to keylength
out = max(lis, key = len)

# Output list Initialization
output = []

for elem in out:
    output.append(elem[0])
    output.append(elem[1])

# Converting to set
output = list(set(output))

# Sorting output
output.sort()

# Printing answer
print("Initial list is ")
print(Input)
print("Longest Consecutive list is:")
print(output)
```

**输出:**

```py
Initial list is 
[1, 2, 3, 5, 6, 6, 7, 9, 10, 11, 13, 14, 15, 16, 16, 17, 18, 20, 21]
Longest Consecutive list is:
[13, 14, 15, 16]
```