# Python–极值差异最小的行

> 原文:[https://www . geeksforgeeks . org/python-极小差值行/](https://www.geeksforgeeks.org/python-row-with-minimum-difference-in-extreme-values/)

给定一个矩阵，提取极值差异最小的行。

**示例:**

> **输入** : test_list = [[4，10，18]，[5，0]，[1，4，6]，[19，2]]
> **输出** : [[1，4，6]，[5，0]]
> **解释**:6–1 = 5，5–0 = 5，是极值之间的最小差。
> 
> **输入** : test_list = [[4，10，18]，[5，0]，[2，4，6]，[19，2]]
> **输出** : [[2，4，6]]
> **解释**:6–2 = 4，为 min diff。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)

在这种情况下，我们计算极值之间最小差值，然后使用列表理解来获得具有极值之间差值的特定行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Matrix Minimum difference in extreme values row
# Using min() + list comprehension

# initializing list
test_list = [[4, 10, 18], [5, 3, 10], [1, 4, 6], [19, 2]]

# printing original list
print("The original list is : " + str(test_list))

# getting min value 
min_val = min([max(sub) - min(sub) for sub in test_list])

# using list comprehension to filter 
res = [sub for sub in test_list if max(sub) - min(sub) == min_val]

# printing result 
print("Rows with Minimum difference in extreme values : " + str(res))
```

**输出:**

> 原始列表为:[[4，10，18]，[5，3，10]，[1，4，6]，[19，2]]
> 极值差异最小的行:[[1，4，6]]

**方法 2:使用**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**过滤器()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[T21】lambda](https://www.geeksforgeeks.org/python-lambda/)

在本例中，我们使用 filter() + lambda 执行与最小值进行比较的过滤任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Matrix Minimum difference in extreme values row
# Using min() + list comprehension + filter() + lambda

# initializing list
test_list = [[4, 10, 18], [5, 3, 10], [1, 4, 6], [19, 2]]

# printing original list
print("The original list is : " + str(test_list))

# getting min value 
min_val = min([max(sub) - min(sub) for sub in test_list])

# using filter() + lambda to filter 
res = list(filter(lambda sub : max(sub) - min(sub) == min_val, test_list))

# printing result 
print("Rows with Minimum difference in extreme values : " + str(res))
```

**输出:**

> 原始列表为:[[4，10，18]，[5，3，10]，[1，4，6]，[19，2]]
> 极值差异最小的行:[[1，4，6]]