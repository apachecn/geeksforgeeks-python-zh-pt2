# Python–矩阵行子集

> 原文:[https://www.geeksforgeeks.org/python-matrix-row-subset/](https://www.geeksforgeeks.org/python-matrix-row-subset/)

有时，在使用 Python Matrix 时，可能会遇到一个问题，即需要提取其他 Matrix 的任何行的可能子集的所有行。这种问题可以在数据领域中应用，因为矩阵是这些领域中的关键数据类型。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_list = [[4，5，7]，[2，3，4]，[9，8，6]]，check_matr = [[2，3]，[1，2]，[9，0]]
> **输出** : [[2，3]]
> 
> **输入** : test_list = [[4，1，2]，[2，3，4]，[9，8，0]]，check_matr = [[2，3]，[1，2]，[9，0]]
> **输出** : [[2，3]，[1，2]，[9，0]]

**方法#1:使用`any() + all()` +列表理解**
以上功能的组合提供了一种解决这个问题的方法。在这种情况下，我们使用 all()检查行中所有元素的出现，any()用于匹配矩阵的任何行。列表理解是用来把逻辑联系在一起的。

```
# Python3 code to demonstrate working of 
# Matrix Row subset
# Using any() + all() + list comprehension

# initializing lists
test_list = [[4, 5, 7], [2, 3, 4], [9, 8, 0]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check Matrix
check_matr = [[2, 3], [1, 2], [9, 0]]

# Matrix Row subset
# Using any() + all() + list comprehension
res = [ele for ele in check_matr if any(all(a in sub for a in ele)
                                           for sub in test_list)]

# printing result 
print("Matrix row subsets : " + str(res)) 
```

**Output :**

```
The original list is : [[4, 5, 7], [2, 3, 4], [9, 8, 0]]
Matrix row subsets : [[2, 3], [9, 0]]

```

**方法二:使用`product() + set()` +列表理解**
以上功能组合可用于此任务。在本文中，我们使用 product()和 set()转换执行嵌套循环的任务是检查一个容器的子集是否在另一个之上。列表理解是用来把所有的联系在一起的。

```
# Python3 code to demonstrate working of 
# Matrix Row subset
# Using product() + set() + list comprehension
import itertools

# initializing lists
test_list = [[4, 5, 7], [2, 3, 4], [9, 8, 0]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check Matrix
check_matr = [[2, 3], [1, 2], [9, 0]]

# Matrix Row subset
# Using product() + set() + list comprehension
res = [a for a, b in itertools.product(check_matr, test_list)
                                         if set(a) <= set(b)]

# printing result 
print("Matrix row subsets : " + str(res)) 
```

**Output :**

```
The original list is : [[4, 5, 7], [2, 3, 4], [9, 8, 0]]
Matrix row subsets : [[2, 3], [9, 0]]

```