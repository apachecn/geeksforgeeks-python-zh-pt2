# Python |前 N 个匹配条件求和

> 原文:[https://www . geeksforgeeks . org/python-第一个匹配条件求和/](https://www.geeksforgeeks.org/python-summation-of-first-n-matching-condition/)

列表中元素的求和可以使用许多内置函数来执行。正规求和函数在各个领域都有许多应用。本文讨论如何对符合特定条件的前 N 个元素进行求和。

**方法#1:天真方法**
我们可以对匹配条件的元素求和，在 N 次元素出现后，我们可以停止操作。下面的代码演示了相同的内容。

```py
# Python 3 code to demonstrate 
# Summation of first N matching condition
# using Naive Method 

# initializing list
test_list = [3, 5, 1, 6, 7, 9, 8, 5]

# printing original list
print ("The original list is : " + str(test_list))

# using Naive Method 
# Summation of first N matching condition
# sums first 3 odd occurrences
counter = 1
res = 0
for i in test_list:
    if counter <= 3 and (i % 2 != 0):
        res = res + i
        counter = counter + 1

# printing result
print ("The filtered list is : " + str(res))
```

**Output :**

```py
The original list is : [3, 5, 1, 6, 7, 9, 8, 5]
The filtered list is : 9

```