# Python 程序寻找矩阵每行的冗余率

> 原文:[https://www . geesforgeks . org/python-program-to-find-矩阵每行的冗余率/](https://www.geeksforgeeks.org/python-program-to-find-the-redundancy-rates-for-each-row-of-a-matrix/)

给定一个矩阵，任务是编写一个 python 程序，可以计算每行的冗余率，即重复字符总数的比率。

**冗余率**:元素重复率。

**公式:**

```
1 - (total unique elements) / (total elements)
```

**示例:**

> **输入:** test_list = [[4，5，2，4，3]，[5，5，5，5，5，5]，[8，7，8，8，7]，[1，2，3，4，5]]
> 
> **输出:**【0.19999999999999996，0.8，0.6，0.0】
> 
> **说明:**1 –[ 2/5]= 0.6，第三排。
> 
> **输入:** test_list = [[5，5，5，5，5]，5]，[8，7，8，8，7]，[1，2，3，4，5]]
> 
> **输出:**【0.8，0.6，0.0】
> 
> **说明:**1 –[ 2/5]=第二行 0.6。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*设置()*](https://www.geeksforgeeks.org/python-sets/)

在这种情况下，我们使用集合长度计算的唯一元素的分数，对列表中的所有元素执行计算速率的任务，从 1 中减去。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = [[4, 5, 2, 4, 3], [5, 5, 5, 5, 5],
             [8, 7, 8, 8, 7], [1, 2, 3, 4, 5]]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # getting Redundancy
    res.append(1 - len(set(sub)) / len(sub))

# printing result
print("Matrix Redundancy ? : " + str(res))
```

**输出:**

> 原来的名单是:[[4，5，2，4，3]，[5，5，5，5，5]，[8，7，8，8，7]，[1，2，3，4，5]]
> 
> 矩阵冗余？: [0.19999999999999996, 0.8, 0.6, 0.0]

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

使用与上述方法类似的功能，唯一的区别是它的一个线性解决方案使用列表理解计算。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = [[4, 5, 2, 4, 3], [5, 5, 5, 5, 5],
             [8, 7, 8, 8, 7], [1, 2, 3, 4, 5]]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension for one liner
res = [1 - len(set(sub)) / len(sub) for sub in test_list]

# printing result
print("Matrix Redundancy ? : " + str(res))
```

**输出:**

> 原来的名单是:[[4，5，2，4，3]，[5，5，5，5，5]，[8，7，8，8，7]，[1，2，3，4，5]]
> 
> 矩阵冗余？: [0.19999999999999996, 0.8, 0.6, 0.0]