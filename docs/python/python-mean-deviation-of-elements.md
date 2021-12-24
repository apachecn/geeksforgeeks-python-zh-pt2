# Python–元素的平均偏差

> 原文:[https://www . geeksforgeeks . org/python-元素平均偏差/](https://www.geeksforgeeks.org/python-mean-deviation-of-elements/)

给定一个列表，任务是编写一个 Python 程序来计算它们中的每一个与其列表均值的偏离程度。

**示例:**

> **输入**:test _ list =【7，5，1，2，10，3】
> **输出**:【2.333333333333，0.333333333304，3.66666666666
> 
> **输入** : test_list = [1，2，3，4，5]
> **输出**:【2，1，0，1，2】
> **解释**:均值为 3，计算相关差值。

**方法#1:使用循环+平均值()+绝对值()**

在这种情况下，我们执行每个元素的迭代，并使用 abs()计算与平均值的偏差，使用 mean()计算平均值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Mean deviation of Elements
# Using loop + mean() + abs()
from statistics import mean

# initializing list
test_list = [7, 5, 1, 2, 10, 3]

# printing original lists
print("The original list is : " + str(test_list))

res = []

# getting mean
mean_val = mean(test_list)

for ele in test_list:

    # getting deviation
    res.append(abs(ele - mean_val))

# printing result
print("Mean deviations : " + str(res))
```

**输出:**

> 原来的名单是:【7，5，1，2，10，3】
> 平均偏差:【2.33333333333333333333304，3.666666666666，2.6666667，5.333333333333，3.6666666

**方法 2:使用列表理解+均值()**

在本例中，类似的功能被用作上述功能，不同的是列表理解被用作解决这个问题的一行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Mean deviation of Elements
# Using list comprehension + mean()
from statistics import mean

# initializing list
test_list = [7, 5, 1, 2, 10, 3]

# printing original lists
print("The original list is : " + str(test_list))

res = []

# getting mean
mean_val = mean(test_list)

# list comprehension used for 1 liner
res = [abs(ele - mean_val) for ele in test_list]

# printing result
print("Mean deviations : " + str(res))
```

**输出:**

> 原来的名单是:【7，5，1，2，10，3】
> 平均偏差:【2.33333333333333333333304，3.666666666666，2.6666667，5.333333333333，3.6666666